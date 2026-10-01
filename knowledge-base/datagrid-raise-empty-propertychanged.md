---
title: Refreshing DataGrid Grouping, Sorting, and Aggregates with an Empty PropertyChanged
description: Learn how to make the DataGrid for MAUI re-evaluate grouping, sorting, and aggregates for a silently mutated item by raising PropertyChanged without a property name.
type: how-to
page_title: How to Raise PropertyChanged Without a PropertyName to Refresh the MAUI DataGrid
slug: datagrid-raise-empty-propertychanged
tags: datagrid, maui, propertychanged, inotifypropertychanged, grouping, sorting, aggregate, footer, refresh
res_type: kb
---

## Environment

| Version | Product | 
| --- | --- | 
| 15.1.0 | DataGrid for .NET MAUI | 

## Description

I have a `RadDataGrid` bound to a collection of items that implement `INotifyPropertyChanged`. In some scenarios I update several properties of an item at once (for example, during a batch update) without raising `PropertyChanged` for each individual property.

After the update, the grid still shows the item in its old group, in its old sort position, and the column footer aggregate still reflects the old value. I do not want to raise a separate `PropertyChanged` notification for every property that changed.

This knowledge base article also answers the following questions:
- How can I force the DataGrid to re-apply grouping and sorting after mutating an item silently?
- How do I refresh column footer aggregates without raising a notification per property?
- What does raising `PropertyChanged` with an empty property name do in the DataGrid?

## Solution

The `RadDataGrid` subscribes to the `INotifyPropertyChanged.PropertyChanged` event of the items in its `ItemsSource`. When you raise `PropertyChanged` with an **empty property name** (either `null` or `String.Empty`), the .NET convention states that *all* properties on the object have changed. The DataGrid honors this convention and re-applies its data operations—grouping, sorting, and aggregation/footer—for that item.

This allows you to mutate many properties at once without raising a notification per property, and then trigger a single refresh by raising one `PropertyChanged(String.Empty)`.

**1.** Create a data model that implements `INotifyPropertyChanged`. Expose a method that changes the backing fields silently (without raising notifications), and a method that raises `PropertyChanged` with any property name, including an empty one:

```csharp
using System.ComponentModel;

public class DataItem : INotifyPropertyChanged
{
    private string category;
    private bool isVisible;
    private string name;
    private int score;

    public DataItem(string name, string category, bool isVisible, int score)
    {
        this.name = name;
        this.category = category;
        this.isVisible = isVisible;
        this.score = score;
    }

    public event PropertyChangedEventHandler PropertyChanged;

    public string Category => this.category;

    public bool IsVisible => this.isVisible;

    public string Name => this.name;

    public int Score => this.score;

    public void RaisePropertyChanged(string propertyName)
    {
        this.PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(propertyName));
    }

    // Updates all the backing fields WITHOUT raising PropertyChanged.
    public void SetValuesSilently(string name, string category, bool isVisible, int score)
    {
        this.name = name;
        this.category = category;
        this.isVisible = isVisible;
        this.score = score;
    }
}
```

**2.** Define the `RadDataGrid` with its columns and a `PropertyAggregateDescriptor` (Sum) on the numeric column so a footer aggregate is displayed:

```xaml
<Grid Padding="12"
        RowDefinitions="Auto, *">
    <VerticalStackLayout Spacing="8">
        <Label x:Name="instructionsLabel"
                Text="Tap 'Mutate Silently' to change an item without raising PropertyChanged. Then tap 'Raise Empty PropertyChanged' to make the grid reapply group, sort, and aggregate logic." />
        <HorizontalStackLayout Spacing="8">
            <Button Text="Mutate Silently"
                    Clicked="OnMutateSilentlyClicked" />
            <Button Text="Raise Empty PropertyChanged"
                    Clicked="OnRaiseEmptyPropertyChangedClicked" />
        </HorizontalStackLayout>
    </VerticalStackLayout>

    <telerik:RadDataGrid x:Name="grid"
                         Grid.Row="1"
                         AutoGenerateColumns="False"
                         ShowColumnFooters="True"
                         UserGroupMode="Enabled">
        <telerik:RadDataGrid.Columns>
            <telerik:DataGridTextColumn PropertyName="Name"
                                        HeaderText="Name" />
            <telerik:DataGridTextColumn PropertyName="Category"
                                        HeaderText="Category" />
            <telerik:DataGridBooleanColumn PropertyName="IsVisible"
                                           HeaderText="Visible" />
            <telerik:DataGridNumericalColumn PropertyName="Score"
                                             HeaderText="Score">
                <telerik:DataGridNumericalColumn.AggregateDescriptors>
                    <telerik:PropertyAggregateDescriptor PropertyName="Score"
                                                         Caption="Score Sum:"
                                                         Function="Sum" />
                </telerik:DataGridNumericalColumn.AggregateDescriptors>
            </telerik:DataGridNumericalColumn>
        </telerik:RadDataGrid.Columns>
    </telerik:RadDataGrid>
</Grid>
```

**3.** Populate the grid and configure its sort and group descriptors in the code-behind:

```csharp
using System.Collections.ObjectModel;
using Telerik.Maui.Controls.Data;
using Telerik.Maui.Controls.DataGrid;

private ObservableCollection<DataItem> items;
private DataItem deferredItem;

public MainPage()
{
    InitializeComponent();

    this.items = this.CreateItems();
    this.grid.ItemsSource = this.items;
    this.ConfigureDescriptors();
}

private void ConfigureDescriptors()
{
    this.grid.SortDescriptors.Clear();
    this.grid.SortDescriptors.Add(new PropertySortDescriptor
    {
        PropertyName = nameof(DataItem.Name),
        SortOrder = SortOrder.Ascending
    });

    this.grid.GroupDescriptors.Clear();
    this.grid.GroupDescriptors.Add(new PropertyGroupDescriptor
    {
        PropertyName = nameof(DataItem.Category)
    });
}

private ObservableCollection<DataItem> CreateItems()
{
    this.deferredItem = new DataItem("Webcam", "Accessories", false, 5);

    return new ObservableCollection<DataItem>
    {
        new DataItem("Laptop Stand", "Accessories", true, 15),
        new DataItem("HDMI Cable", "Cables", true, 30),
        this.deferredItem,
    };
}
```

**4.** Change several properties of the item without raising any notifications. At this point the grid still shows the old group, sort position, and footer sum:

```csharp
private void OnMutateSilentlyClicked(object sender, EventArgs e)
{
    // No PropertyChanged is raised here, so the grid does not update yet.
    this.deferredItem.SetValuesSilently("Docking Station", "Peripherals", true, 60);
}
```

Raise a single `PropertyChanged` with an empty property name. The grid re-applies grouping, sorting, and aggregation for the item—it moves from the `Accessories` group to the `Peripherals` group, re-sorts to the top (Docking Station), and the footer `Score Sum` recalculates:

```csharp
private void OnRaiseEmptyPropertyChangedClicked(object sender, EventArgs e)
{
    // string.Empty (or null) signals that all properties changed,
    // prompting the grid to re-evaluate group, sort, and aggregate logic.
    this.deferredItem.RaisePropertyChanged(string.Empty);
}
```

## Notes

- Both `null` and `String.Empty` follow the same "all properties changed" convention and produce the same refresh behavior.
- Raising an empty `PropertyChanged` re-evaluates data operations only for the item that raised it. To refresh the entire data view, reset the `ItemsSource` or update the grid's data descriptor collections.
- Prefer raising `PropertyChanged` for the specific property (`nameof(...)`) during normal single-property updates. Use the empty-name approach when several properties change at once and you want a single notification.

## See Also

- [DataGrid Grouping]({%slug datagrid-grouping-overview%})
- [DataGrid Sorting]({%slug datagrid-sorting-overview%})
- [DataGrid Aggregates]({%slug datagrid-aggregates%})
