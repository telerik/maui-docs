---
title: Conditionally Showing or Hiding the Expand Arrow in Toggle Row Details Column Cells
description: Learn how to conditionally show or hide the expand arrow in the toggle row details column cells in the DataGrid for UI for .NET MAUI when there are no details for the rows.
type: how-to
page_title: Conditionally Display Expand Arrow in DataGrid Toggle Row Details Column
meta_title: Conditionally Display Expand Arrow in DataGrid Toggle Row Details Column
slug: conditionally-show-hide-expand-arrow-datagrid
tags: datagrid, ui-for-net-maui, toggle-row-details-column, isvisible-property, cellcontentstyleselector
res_type: kb
ticketid: 1700211
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.1.0 | Telerik UI for .NET MAUI DataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

## Description

I want to conditionally hide the expand arrow in the toggle row details column cells when there are no details for the rows in the DataGrid for UI for .NET MAUI.

This knowledge base article also answers the following questions:
- How to hide the expand arrow in DataGrid for UI for .NET MAUI when no row details exist?
- How to implement conditional visibility for the toggle row details button?
- How to stop default command execution for empty row details?

## Solution

To hide the expand arrow in the toggle row details column cells when no row details exist, follow these steps:

1. Implement a custom style selector to apply different styles based on whether the row has details.

```csharp
public class RowDetailsColumnStyleSelector : IStyleSelector
{
    public Style Style1 { get; set; }
    public Style Style2 { get; set; }

    public Style SelectStyle(object item, BindableObject bindable)
    {
        var dataItem = (DataGridCellInfo)item;
        if (dataItem.Item is Data data)
        {
            if (string.IsNullOrEmpty(data.Details))
            {
                return this.Style1; // Apply transparent button style when no details exist.
            }
        }
        return this.Style2; // Apply default button style.
    }
}
```

2. Define styles for the toggle row details column cells in your XAML.

```xml
<ContentPage.Resources>
    <ResourceDictionary>
        <!-- Define RowDetailsCellStyleSelector -->
        <local:RowDetailsColumnStyleSelector x:Key="RowDetailsCellStyleSelector">
            <local:RowDetailsColumnStyleSelector.Style1>
                <Style TargetType="telerik:DataGridToggleRowDetailsCellAppearance">
                    <Setter Property="ButtonTextColor" Value="Transparent" />
                    <Setter Property="ButtonFontSize" Value="0" />
                </Style>
            </local:RowDetailsColumnStyleSelector.Style1>
            <local:RowDetailsColumnStyleSelector.Style2>
                <Style TargetType="telerik:DataGridToggleRowDetailsCellAppearance">
                    <Setter Property="ButtonTextColor" Value="Black" />
                </Style>
            </local:RowDetailsColumnStyleSelector.Style2>
        </local:RowDetailsColumnStyleSelector>

        <!-- Apply CellContentStyleSelector to ToggleRowDetailsColumn -->
        <Style TargetType="telerik:DataGridToggleRowDetailsColumn">
            <Setter Property="CellContentStyleSelector" Value="{StaticResource RowDetailsCellStyleSelector}" />
        </Style>
    </ResourceDictionary>
</ContentPage.Resources>
```

3. Implement a custom `ToggleRowDetailsButtonTap` command to prevent the default behavior when row details are empty.

```csharp
public class MyToggleRowDetailsButtonTap : DataGridCommand
{
    public MyToggleRowDetailsButtonTap()
    {
        Id = DataGridCommandId.ToggleRowDetailsButtonTap;
    }

    public override bool CanExecute(object parameter)
    {
        return true;
    }

    public override void Execute(object parameter)
    {
        var data = parameter as Data;
        if (string.IsNullOrEmpty(data?.Details))
        {
            return; // Prevent default execution when no row details exist.
        }
        this.Owner.CommandService.ExecuteDefaultCommand(DataGridCommandId.ToggleRowDetailsButtonTap, parameter);
    }
}
```

4. Set up the `RadDataGrid` and link the resources.

```xml
<telerik:RadDataGrid x:Name="dataGrid"
                     AutoGenerateColumns="False"
                     RowDetailsTemplate="{StaticResource TemplateForRowDetails}">
    <telerik:RadDataGrid.Columns>
        <telerik:DataGridToggleRowDetailsColumn CanUserReorder="False"/>
        <telerik:DataGridTextColumn PropertyName="Country" />
        <telerik:DataGridTextColumn PropertyName="Capital" />
    </telerik:RadDataGrid.Columns>
</telerik:RadDataGrid>
```

In the code behind, assign the `ItemsSource` and add the custom command.

```csharp
List<Data> items = new List<Data>
{
    new Data { Country = "India", Capital = "New Delhi", Details = "Details about India." },
    new Data { Country = "South Africa", Capital = "Cape Town", Details = "Details about South Africa." },
    new Data { Country = "Nigeria", Capital = "Abuja", Details = "Details about Nigeria." },
    new Data { Country = "Singapore", Capital = "Singapore" }
};

this.dataGrid.ItemsSource = items;
this.dataGrid.Commands.Add(new MyToggleRowDetailsButtonTap());
```

## See Also

- [DataGrid Overview](https://www.telerik.com/maui-ui/documentation/controls/datagrid/overview)
- [CellContentStyleSelector Documentation](https://www.telerik.com/maui-ui/documentation/controls/datagrid/theming-and-styles/style-selectors)
