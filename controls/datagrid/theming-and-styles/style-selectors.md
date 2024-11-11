---
title: Style Selectors
page_title: .NET MAUI DataGrid Documentation - Style Selectors
description: Check our &quot;Style Selectors&quot; documentation article for Telerik DataGrid for .NET MAUI control.
position: 3
previous_url: /controls/datagrid/theming-and-styles/datagrid-style-selectors
slug: datagrid-style-selectors
---

# .NET MAUI DataGrid Style Selectors

The [.NET MAUI DataGrid]({%slug datagrid-overview%}) component exposes a conditional styling feature. It allows users to apply different styles on a cell or per group header depending on a specific condition.

You can set a different style on a specific cell from a specific column based on custom selection logic with the following properties:

* `CellContentStyleSelector`(`IStyleSelector`)&mdash;Styles the content of the cell by using the text alignment options (`TextMargin`, `HorizontalTextAlignment`, `VerticalTextAlignment`), the font options (`FontAttributes`, `FontFamily`, `FontSize`) and the `TextColor` property.
* `CellDecorationStyleSelector`(`IStyleSelector`)&mdash;Styles the decoration of a cell.

Different styles can be applied on a per-group header once the DataGrid control is grouped through `GroupHeaderStyleSelector` property.

Different styles can be applied on a per-group footer once the DataGrid control is grouped through `GroupFooterStyleSelector` property.

> To display the group footer, set the `ShowGroupFooters` property to `True`.

The `CellContentStyleSelector`, `CellDecorationStyleSelector`, and `GroupStyleSelector` use the `SelectStyle` method to change the style.

## Example

The following example will demonstrate how to apply the style selectors in the DataGrid control:

Let’s add the DataGrid and set the `CellContentStyleSelector` as a static resource of type `MyCellContentStyleSelector`, `CellDecorationStyleSelector` as a static resource of type `MyCellDecorationStyleSelector`, and `GroupStyleSelector` as a static resource of type `MyGroupStyleSelector`.

**1.** `DataGrid` definition in XAML:

<snippet id='datagrid-styleselector-example'/>

**2.** Create a simple data for the DataGrid:

<snippet id='datagrid-styleselector-data'/>

**3.** Set the `ItemsSource` of the `DataGrid` class:

<snippet id='datagrid-styleselector-items'/>


**4.** Add `MyCellContentStyleSelector`, `MyCellDecorationStyleSelector`, and `MyGroupStyleSelector` as resources in the **Resource** page of the application:

<snippet id='datagrid-styleselectors'/>

**5.** Create a custom class for each selector. This class derives from `DataGridStyleSelector` and overrides its `SelectStyle` method.

The `MyCellContentStyleSelector` class implementation is as follows:

<snippet id='datagrid-styleselector-cellcontent'/>

The implementation of the `MyCellDecorationStyleSelector` class is shown below:

<snippet id='datagrid-styleselector-celldecoration'/>


You can implement `MyGroupStyleSelector` as follows:

<snippet id='datagrid-styleselector-group'/>


This is how the DataGrid control will look when `CellContentStyleSelector` is applied.

![DataGrid StyleSelectors](../images/datagrid-style-selector.png)

## See Also

- [DataGrid Styling]({%slug datagrid-styling%})
- [Columns Styling]({%slug datagrid-columns-styling%})
