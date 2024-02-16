---
title: Specifying the Binding for a CellContentTemplate in Telerik .NET MAUI DataGrid with DataTable
description: This article explains how to specify the binding for a CellContentTemplate when using the .NET MAUI DataGrid DataTable.
type: how-to
page_title: Specifying the Binding for a CellContentTemplate DataTemplate
slug: specifying-binding-cellcontenttemplate-datatable
tags: DataGrid, DataTable, binding, template, dotnet, maui
res_type: kb
---
# Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 6.7.0 | Telerik UI for .NET MAUI DataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

# Description

When using a `CellContentTemplate` with the `RadDataGrid` that uses a `DataTable` as a source, you need to specify the binding for the template. This article provides an example of how to do this.

# Solution

To specify the binding for a `CellContentTemplate` follow these steps:

1. Define the RadDataGrid and set its `ItemsSource` property to the data source.
2. Create the necessary columns and specify the `PropertyName` for each column.
3. Inside the `CellContentTemplate` of the desired column, define the desired control and bind it to the appropriate property using the indexer syntax&mdash;`[PropertyName]`.

Here is an example of a `RadDataGrid` with two columns and binding in the template in XAML and C#:

```xaml
<telerik:RadDataGrid ItemsSource="{Binding Data}" AutoGenerateColumns="False">
    <telerik:RadDataGrid.BindingContext>
        <local:DataTableViewModel/>
    </telerik:RadDataGrid.BindingContext>
    <telerik:RadDataGrid.Columns>
        <telerik:DataGridTextColumn PropertyName="City">
            <telerik:DataGridTextColumn.CellContentTemplate>
                <DataTemplate>
                    <Label Text="{Binding [City]}"/>
                </DataTemplate>
            </telerik:DataGridTextColumn.CellContentTemplate>
        </telerik:DataGridTextColumn>
        <telerik:DataGridBooleanColumn PropertyName="IsVisited">
            <telerik:DataGridBooleanColumn.CellContentTemplate>
                <DataTemplate>
                    <telerik:RadCheckBox IsChecked="{Binding [IsVisited]}"/>
                </DataTemplate>
            </telerik:DataGridBooleanColumn.CellContentTemplate>
        </telerik:DataGridBooleanColumn>
    </telerik:RadDataGrid.Columns>
</telerik:RadDataGrid>
```
```C#
public partial class MainPage : ContentPage
{
    DataTableViewModel vm;
    public MainPage()
    {
        InitializeComponent();
        this.vm = new DataTableViewModel();
        this.BindingContext = this.vm;

        var grid = new RadDataGrid();
        grid.AutoGenerateColumns = false;
        grid.ItemsSource = this.vm.Data;
        var textColumn = new DataGridBooleanColumn { PropertyName = "City" };
        textColumn.CellContentTemplate = new DataTemplate(() =>
        {
            Label label = new Label();
            label.SetBinding(Label.TextProperty, new Binding("[City]"));
            return label;
        });
        var checkedColumn = new DataGridBooleanColumn { PropertyName = "IsVisited" };
        checkedColumn.CellContentTemplate = new DataTemplate(() =>
        {
            RadCheckBox checkBox = new RadCheckBox();
            checkBox.SetBinding(RadCheckBox.IsCheckedProperty, new Binding("[IsVisited]"));
            return checkBox;
        });
        grid.Columns.Add(textColumn);
        grid.Columns.Add(checkedColumn);

        this.Content = grid;
    }
}
```

Make sure to add the `PropertyName` to each column to specify the binding. In this example, the `City` column is a `DataGridTextColumn`, and the `IsVisited` column is a `DataGridBooleanColumn`.

Create a `ViewModel` class to provide the data source for the `RadDataGrid`. Here is an example of the `ViewModel`:

```csharp
public class DataTableViewModel : NotifyPropertyChangedBase
{
    private DataTable data;

    public DataTableViewModel()
    {
        this.Data = this.GetData();
    }

    public DataTable Data
    {
        get { return this.data; }
        set { this.UpdateValue(ref this.data, value); }
    }

    private DataTable GetData()
    {
        DataTable country = new DataTable();
        country.TableName = "Cities";
        country.Columns.Add("Id", typeof(int));
        country.Columns.Add("City", typeof(string));
        country.Columns.Add("Population", typeof(int));
        country.Columns.Add("Visited On", typeof(DateTime));
        country.Columns.Add("IsVisited", typeof(bool));

        country.Rows.Add(0, "Sofia", 2000000, new DateTime(2012, 10, 1), true);
        country.Rows.Add(1, "New York", 8419000, null, false);
        country.Rows.Add(2, "London", 8982000, new DateTime(2019, 02, 11), true);
        country.Rows.Add(3, "Los Angeles", 3967000, null, false);
        country.Rows.Add(4, "Budapest", 1765000, new DateTime(2013, 02, 1), true);
        country.Rows.Add(5, "Tokyo", 9375104, new DateTime(2015, 09, 1), true);

        return country;
    }
}
```

# Notes

- The indexer syntax `[PropertyName]` is used to bind to a specific property in the DataRowView.
- Make sure to set the `PropertyName` for each column to specify the binding.

# See Also

- [DataGrid DataTable Support](https://docs.telerik.com/devtools/maui/controls/datagrid/datatable-support)
