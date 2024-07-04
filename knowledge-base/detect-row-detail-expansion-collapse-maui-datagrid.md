---
title: Detecting Row Detail Expansion or Collapse in DataGrid for MAUI
description: Learn how to identify when a row detail in the DataGrid for .NET MAUI is expanded or collapsed using MVVM.
type: how-to
page_title: How to Detect Row Detail Expansion or Collapse in .NET MAUI DataGrid
slug: detect-row-detail-expansion-collapse-maui-datagrid
tags: datagrid, rowdetails, expandedrowdetails, toggle, mvvm, maui
res_type: kb
---

## Environment

| Product | Version | Author |
| --- | --- |
| DataGrid for .NET MAUI | 7.0.0 | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

## Description

In a MAUI application using the DataGrid, I need to detect when a row detail is expanded or collapsed while following the MVVM pattern.

This KB article also answers the following questions:
- How can I listen to row detail state changes in a DataGrid?
- Is there a way to bind the expansion state of row details in DataGrid to a ViewModel?
- Can I use MVVM to track the expansion and collapse of row details in DataGrid?

## Solution

To detect when a row detail is expanded or collapsed in the [DataGrid]({%slug datagrid-overview%}) for MAUI using MVVM, you can employ the following approaches:

* Working with the `ExpandedRowDetails` collection
* Using the `ToggleRowDetailsButtonTap` command

### Approach 1: Using the `ExpandedRowDetails` Collection

**1.** Bind the `ExpandedRowDetails` property of the DataGrid to an observable collection in the ViewModel. This collection holds the items for which the row details are currently expanded.

```
<ContentPage.Resources>
    <ResourceDictionary>
        <DataTemplate x:Key="TemplateForRowDetails">
            <VerticalStackLayout BackgroundColor="#F2EFF9"
                Padding="12">
                <Label Text="{Binding Country}" />
                <Label Text="{Binding Capital}" />
                <Label Text="{Binding Details}" />
            </VerticalStackLayout>
        </DataTemplate>
    </ResourceDictionary>
</ContentPage.Resources>
<Grid>
    <telerik:RadDataGrid x:Name="dataGrid"
                            ItemsSource="{Binding Items}"
                            ExpandedRowDetails="{Binding ExpandedItems}"
                            AutoGenerateColumns="False"
                            RowDetailsTemplate="{StaticResource TemplateForRowDetails}">
        <telerik:RadDataGrid.Columns>
            <telerik:DataGridToggleRowDetailsColumn />
            <telerik:DataGridTextColumn PropertyName="Country" />
        </telerik:RadDataGrid.Columns>
    </telerik:RadDataGrid>
</Grid>
```
**2.** Monitor the `CollectionChanged` event of the observable collection. Additions to the collection indicate row detail expansions, while removals indicate collapses. Implement the required logic within the event handler to respond to these changes.

```C#
public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();
        this.BindingContext = new ViewModel();
    }
}

public class ViewModel : NotifyPropertyChangedBase
{
    public ViewModel()
    {
        var items = new ObservableCollection<Data>
        {
            new Data { Country = "India", Capital = "New Delhi" , Details = "New Delhi is the capital of India and a part of the National Capital Territory of Delhi (NCT). New Delhi is the seat of all three branches of the Government of India, hosting the Rashtrapati Bhavan, Sansad Bhavan, and the Supreme Court."},
            new Data { Country = "South Africa", Capital = "Cape Town", Details = "Cape Town is South Africa's oldest city. It serves as the country's legislative capital, being the seat of the South African Parliament.It is the country's second-largest city (after Johannesburg) and the largest in the Western Cape."},
            new Data { Country = "Nigeria", Capital = "Abuja" , Details = "Abuja is the capital city of Nigeria. When it was decided to move the national capital from Lagos in 1976, a capital territory was chosen for its location near the centre of the country. The planned city is located in the centre of what is now the Federal Capital Territory." },
            new Data { Country = "Singapore", Capital = "Singapore" , Details = "Singapore is the capital city of the Republic of Singapore. It occupies the southern part of Singapore Island. Its strategic position on the strait between the Indian Ocean and South China Sea, complemented by its deepwater harbour, has made it the largest port in Southeast Asia." }
        };

        this.Items = items;

        this.ExpandedItems = new ObservableCollection<Data>();

        // Approach 1
        this.ExpandedItems.CollectionChanged += ExpandedItems_CollectionChanged;
    }

    // Approach 1
    private void ExpandedItems_CollectionChanged(object? sender, System.Collections.Specialized.NotifyCollectionChangedEventArgs e)
    {
        if (e.Action == System.Collections.Specialized.NotifyCollectionChangedAction.Add)
        {
            // your logic here
        }
        else if(e.Action == System.Collections.Specialized.NotifyCollectionChangedAction.Remove)
        {
            // your logic here
        }
    }

    public ObservableCollection<Data> Items { get; set; }

    public ObservableCollection<Data> ExpandedItems { get; set; }
}

public class Data
{
    public string Country { get; set; }
    public string Capital { get; set; }
    public string Details { get; set; }
}
```


### Approach 2: Using the `ToggleRowDetailsButtonTap` Command

**1.** Utilize the `ToggleRowDetailsButtonTap` command provided by the DataGrid. This command is triggered whenever the toggle button for row details is tapped. In the command's execution logic, add a flag or a mechanism to check whether the item related to the toggled row detail is present in the `ExpandedRowDetails` collection. An item's presence indicates an expansion, while its absence indicates a collapse.

Implement the necessary logic based on this condition to handle the expansion or collapse state.

```C#
public class MyToggleRowDetailsButtonTapCommand : DataGridCommand
{
    public MyToggleRowDetailsButtonTapCommand()
    {
        Id = DataGridCommandId.ToggleRowDetailsButtonTap;
    }

    public override bool CanExecute(object parameter)
    {
        return true;
    }

    public override void Execute(object parameter)
    {
        // flag
        bool wasExpanded = this.Owner.ExpandedRowDetails.Contains(parameter);
        this.Owner.CommandService.ExecuteDefaultCommand(DataGridCommandId.ToggleRowDetailsButtonTap, parameter);
    }
}
```

**3.** The `ViewModel` and data model definition:

```C#
public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();
        this.BindingContext = new ViewModel();
    }
}

public class ViewModel : NotifyPropertyChangedBase
{
    public ViewModel()
    {
        var items = new ObservableCollection<Data>
        {
            new Data { Country = "India", Capital = "New Delhi" , Details = "New Delhi is the capital of India and a part of the National Capital Territory of Delhi (NCT). New Delhi is the seat of all three branches of the Government of India, hosting the Rashtrapati Bhavan, Sansad Bhavan, and the Supreme Court."},
            new Data { Country = "South Africa", Capital = "Cape Town", Details = "Cape Town is South Africa's oldest city. It serves as the country's legislative capital, being the seat of the South African Parliament.It is the country's second-largest city (after Johannesburg) and the largest in the Western Cape."},
            new Data { Country = "Nigeria", Capital = "Abuja" , Details = "Abuja is the capital city of Nigeria. When it was decided to move the national capital from Lagos in 1976, a capital territory was chosen for its location near the centre of the country. The planned city is located in the centre of what is now the Federal Capital Territory." },
            new Data { Country = "Singapore", Capital = "Singapore" , Details = "Singapore is the capital city of the Republic of Singapore. It occupies the southern part of Singapore Island. Its strategic position on the strait between the Indian Ocean and South China Sea, complemented by its deepwater harbour, has made it the largest port in Southeast Asia." }
        };

        this.Items = items;

        this.ExpandedItems = new ObservableCollection<Data>();
    }

    public ObservableCollection<Data> Items { get; set; }

    public ObservableCollection<Data> ExpandedItems { get; set; }
}

public class Data
{
    public string Country { get; set; }
    public string Capital { get; set; }
    public string Details { get; set; }
}
```

**4.** Define the DataGrid:

```XAML
<ContentPage.Resources>
    <ResourceDictionary>
        <DataTemplate x:Key="TemplateForRowDetails">
            <VerticalStackLayout BackgroundColor="#F2EFF9"
                Padding="12">
                <Label Text="{Binding Country}" />
                <Label Text="{Binding Capital}" />
                <Label Text="{Binding Details}" />
            </VerticalStackLayout>
        </DataTemplate>
    </ResourceDictionary>
</ContentPage.Resources>
<Grid>
    <telerik:RadDataGrid x:Name="dataGrid"
                            ItemsSource="{Binding Items}"
                            ExpandedRowDetails="{Binding ExpandedItems}"
                            AutoGenerateColumns="False"
                            RowDetailsTemplate="{StaticResource TemplateForRowDetails}">
        <telerik:RadDataGrid.Columns>
            <telerik:DataGridToggleRowDetailsColumn />
            <telerik:DataGridTextColumn PropertyName="Country" />
        </telerik:RadDataGrid.Columns>
        <telerik:RadDataGrid.Commands>
            <local:MyToggleRowDetailsButtonTapCommand />
        </telerik:RadDataGrid.Commands>
    </telerik:RadDataGrid>
</Grid>
```

Both approaches allow for handling row detail expansion and collapse states in a MVVM-compliant manner, enabling you to perform actions or update the UI accordingly.

## See Also

- [DataGrid Commands Overview]({%slug datagrid-commands-overview%}})
- [DataGrid Row Details Documentation]({%slug datagrid-row-details-overview%}})
