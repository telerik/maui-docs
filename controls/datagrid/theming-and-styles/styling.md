---
title: DataGrid Styling
page_title: .NET MAUI DataGrid Documentation - Styling
description: Check our &quot;DataGrid Styling&quot; documentation article for Telerik DataGrid for .NET MAUI control.
position: 0
previous_url: /controls/datagrid/theming-and-styles/datagrid-styling
slug: datagrid-styling
---

# DataGrid Styling

The DataGrid control provides the following `Style` properties for customizing its look & feel:

* `RowBackgroundStyle`&mdash;Defines the style of each row.
* `AlternateRowBackgroundStyle`&mdash;Defines the appearance style of an alternated row.
* `GroupHeaderStyle`&mdash;Defines the appearance style of the group header once the DataGrid is grouped.
* `SelectionStyle`&mdash;Defines the appearance settings applied to the selected DataGrid row.
* `CurrentCellStyle`&mdash;Defines the style applied to the current cell.

## Styling Properties

`RowBackgroundStyle`, `AlternateRowBackgroundStyle`, `SelectionStyle` and `CurrentCellStyle` are of type `DataGridBorderStyle` that defines the appearance settings applied to a `BorderPaintable` instance and exposes the `BackgroundColor`, `BorderColor`, and `BorderTickness` properties.

Example how to set the `RowBackgroundStyle` property:

<snippet id='datagrid-styling-rowbackgroundstyle'/>

Example how to set the `AlternateRowBackgroundStyle` is shown below:

<snippet id='datagrid-styling-alternaterowbackgroundstyle'/>

The `SelectionStyle` property can be set as shown below:

<snippet id='datagrid-styling-selectionstyle'/>

The `CurrentCellStyle` property can be set as shown below:

<snippet id='datagrid-keyboard-navigation-style' />

The `GoupHeaderStyle` property is applied once the DataGrid is grouped.

The following properties can be used for customizing the grouped DataGrid:

* `BackgroundColor`&mdash;Defines the color that fills the area within the header of the DataGrid `GroupHeader`.
* `BorderColor`&mdash;Defines the color that fills the border region of the `GroupHeader`.
* `BorderThickness`&mdash;Defines the thickness of the border.
* `Button Font Options` (`ButtonFontAttributes`, `ButtonFontFamily`, `ButtonFontSize`)&mdash;Define the font options of the `GroupedHeader` expand/collapse symbol.
* `ButtonMargin`&mdash;Defines the margin of the expand/collapse symbol of the `GroupHeader`.
* `ButtonTextColor`&mdash;Defines the text color of the expand/collapse symbol of the `GroupHeader`.
* `CollapseButtonText`&mdash;Defines the text for the collapse state of the `GroupHeader`.
* `ExpandButtonText`&mdash;Defines the text for the expand state of the `GroupHeader`.
* `Text` alignment options (`TextMargin`, `VerticalTextAlignment`, `HorizontalTextAlignment`)&mdash;Define the positioning for the text part of the `GroupHeader`.
* `TextFont` options (`TextFontattributes`, `TextFontFamily`, `TextFontSize`)&mdash;Define the font options of the `GroupHeaders` text part.

>note Note that once the group is applied to the DataGrid, the `GroupHeader` will appear. Also, by default, the Button of the `GroupHeader` uses an internal symbol font family. To show text when the button is expanded or collapsed, instead of a symbol set a font family to the `ButtonFontFamily` property and define text to the `ExpandButtonText` and `CollapseButtonText` properties. For more details, refer to the [group feature of the DataGrid]({%slug datagrid-grouping-overview%}).

Example how to apply the `GoupHeaderStyle` property to the DataGrid control:

<snippet id='datagrid-styling-groupheaderstyle'/>

Here is how the DataGrid looks:

![DataGrid Styling](../images/datagrid-styling.png)

## See Also

- [Columns Styling]({%slug datagrid-columns-styling%})
- [Style Selectors]({%slug datagrid-style-selectors%})
