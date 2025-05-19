---
title: Defining Columns
page_title: .NET MAUI TreeDataGrid Documentation - Defining Columns
description: Lear what are the configuration options you can apply to the columns in the TreeDataGrid for .NET MAUI.
position: 0
slug: treedatagrid-columns-overview
---

{% if site.has_cta_panels == true %}
{% include cta-panel-small.html %}
{% endif %}

# .NET MAUI TreeDataGrid: Defining Columns

The [Telerik UI for .NET MAUI TreeDataGrid]({%slug treedatagrid-overview%}) supports three methods for defining columns, inherited from the [DataGrid]({%slug datagrid-overview%}):

* Automatically&mdash;by setting `AutoGenerateColumns` property to `True` (default value).
* Manually&mdash;by adding columns to the DataGrid's `Columns` collection and setting the `AutoGenerateColumns` property to `False`.
* Mixed&mdash;by adding columns to the `Columns` collection and also setting the `AutoGenerateColumns`to `True` (default value).

## Automatic Columns Generation

By default, the TreeDataGrid generates typed columns automatically based on the underlying data type. When, for example, you set the `ItemsSource` of the `RadDataGrid` to a collection of clubs (see the sample code below), the control will create a separate column for each public property of the `Club` object.

For example, let's have a sample `Club` object:

```XAML
public class Club
{ 
    public string Name { get; set; }
    public DateTime Established { get; set; }
    public bool IsChampion { get; set; }
    public ObservableCollection<Club> Children { get; set; }
}
```

With the automatic columns generation TreeDataGrid will create the following columns:

* `DataGridTextColumn` for the `Name` property.
* `DataGridDateColumn` for the `Established` property.
* `DataGridBooleanColumn` for the `IsChampion` property.
* `DataGridTypedColumn` for the `IsChampion` property.

## Manual Columns Definition

Using the built-in auto generation of columns does not fit all scenarios. In such cases, you can manually define the needed columns. When defining a column, you can choose between several column types:

* [Text Column]({%slug datagrid-columns-text-column%})&mdash;Represents a column that converts the content of each associated cell to a `System.String` object.
* [Numerical Column]({%slug datagrid-columns-numerical-column%})&mdash;Represents an extended `DataGridTextColumn` that presents numerical data (`int` and `double` types).
* [Boolean Column]({%slug datagrid-columns-boolean-column%})&mdash;An extended `DataGridTextColumn` implementation that presents Boolean data.
* [Date Column]({%slug datagrid-columns-date-column%})&mdash;An extended `DataGridTextColumn` that presents data of type `DateTime`.
* [Time Column]({%slug datagrid-columns-time-column%})&mdash;Represents an extended `DataGridTextColumn` that presents the `TimeOfDay` of a `DateTime` type.
* [ComboBox Column]({%slug datagrid-columns-picker-column%})&mdash;Represents an extended `DataGridTextColumn`, whose cell value editor is a `Telerik.Maui.Controls.RadComboBox` control.
* [Template Column]({%slug datagrid-columns-template-column%})&mdash;Represents a column that uses a `DataTemplate` to describe the content of each associated grid cell.
* [ToggleRowDetails Column]({%slug datagrid-columns-toggle-column%})&mdash;Represents a column that allows the user to show and hide the row details for an item.

For the typed columns (Text, Numerical, Boolean, Date, Time and ComboBox) you can define which property of the underlying data object the column represents in the following ways:

* `PropertyName`&mdash;Specifies the name of the property of the data object being displayed in the column's cells.
* `DataMemberBinding`&mdash;Defines the binding which points to the data member of the underlying object being displayed in the column's cell. With `DataMemberBinding`, you have control over the way data is formatted and displayed in the DataGrid cells, for example you can add a string formatter or a value converter.

> For a runnable example with the TreeDataGrid columns, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **TreeDataGrid > Getting Started** category.

## Column Features

Find below a quick overview of the TreeDataGrid's Columns features.

### Column Headers

The top cell of a column is called Header. Its purpose is to set a caption for the column, which describes the data displayed in it. The .NET MAUI TreeDataGrid provides fully customizable column headers, check [Column Headers]({%slug treedatagrid-column-header%}) for detailed information.

### Columns Cell Templates

The TreeDataGrid provides a set of predefined column types such as Text Column, Numerical Column, etc. In case you need to extend the functionality of a column, for example customize the default appearance or add more UI elements, use the exposed templates - `CellContentTemplate` and `CellEditTemplate`. For detailed information, see the [Columns Cells Templates]({%slug treedatagrid-cell-templates%}) topic.

### Column Footers

The TreeDataGrid allows you to display additional information which applies to the columns in a specific row placed at the bottom of the control. This row consists of individual footer cells for each column. Take a look at the [Column Footers]({%slug treedatagrid-column-footer%}) for detailed information.

### Column Resizing

Columns inside the Telerik .NET MAUI TreeDataGrid are resizable by default. The feature is available only on Desktop - WinUI and MacCatalyst. For more details see the [Column Resizing]({%slug datagrid-column-resizing%}) topic.

### Columns Width

The TreeDataGrid provides a flexible mechanism for setting columns' width through columns' `SizeMode` and `Width` properties. For more details see the [Columns Width]({%slug datagrid-columns-width%}) topic.

### Frozen Columns

You can pin a column on the left side of the TreeDataGrid by setting the `IsFrozen` property to the column. By default the value is `False`. When setting it to `True` to a concrete column, it makes the column frozen. For detailed information, see the [Frozen Columns]({%slug treedatagrid-frozen-columns%}) topic.

### Columns Reordering

The TreeDataGrid exposes a reordering feature allowing the user to drag and drop columns and change their order. For more details, see the [Columns Reordering]({%slug datagrid-columns-reordering%}) topic.

>tip For an outline of all TreeDataGrid features review the [.NET MAUI TreeDataGrid Overview]({%slug treedatagrid-overview%}) article.

## See Also

- [Column Headers]({%slug treedatagrid-column-header%})
- [Columns Cells Templates]({%slug treedatagrid-cell-templates%})
- [Column Footers]({%slug treedatagrid-column-footer%})
- [Column Resizing]({%slug treedatagrid-column-resizing%})
- [Columns Width]({%slug treedatagrid-columns-width%})
- [Frozen Columns]({%slug treedatagrid-frozen-columns%})
- [Columns Reordering]({%slug treedatagrid-columns-reordering%})
