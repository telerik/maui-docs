---
title: Aggregate Styling
page_title: .NET MAUI DataGrid Documentation - Aggregate Styling
description: Learn how to style the group footer, header, and column footer of the Telerik UI for .NET MAUI DataGrid when its data is aggregated.
position: 3
slug: datagrid-aggregates-styling
---

# .NET MAUI DataGrid Aggregates Styling

The .NET MAUI DataGrid provides a styling functionality for its group footer, header, and column footer aggregates.

## Styling the Group Header

The [Telerik UI for .NET MAUI DataGrid]({%slug datagrid-overview%}) provides the `GroupHeaderStyle` (of type `Style` with target type `DataGridGroupHeaderAppearance`) configuration which defines the style of the `GroupHeader` and the aggregates inside the header. 

> To visualize the aggregates in the DataGrid group header, set the `ShowGroupHeaderAggregates` to `True`. The property is a property inside the `RadDataGrid` instance.

### Style the Group Header:

Use the following properties to style the GroupHeader:

| Style  | Action |
| ------ | ------ |
| `BackgroundColor` | Defines the color that fills the area within the header |
| `BorderColor`| Defines the color that fills the border region. |
| `BorderThickness` | Defines the thickness of the border. |
| `ButtonFontAttributes` | Defines the font attributes for the expand/collapse symbol for the group headers. |
| `ButtonFontFamily` | Defines the font family for the  expand/collapse symbol of the `GroupHeader`. |
| `ButtonFontSize` | Defines the font size for the expand/collapse symbol of the `GroupHeader`. |
| `ButtonMargin` | Defines the margin for the expand/collapse symbol of the `GroupHeader`. |
| `ButtonTextColor` | Defines the color for the expand/collapse symbol of the `GroupHeader`. |
| `TextColor` | Defines the color for the text part of the `GroupHeader` |
| `TextFontAttributes` | Defines the font attributes for the text part of the `GroupHeader`. |
| `TextFontFamily` | Defines the font family for the text part of the `GroupHeader`. |
| `TextFontSize` | Defines the size for the text part of the `GroupHeader`. |
| `TextMargin` | Defines the margin for the text part of the `GroupHeader`. |

### Style the Aggregate Results

You can style the aggregates results depending on the value set for the `GroupAggregatesAlignment` (`enum` of type `Telerik.Maui.Controls.DataGrid.DataGridGroupAggregatesAlignment`) property.

When the value for the `GroupAggregatesAlignment` is `None`, set the properties described in the table below to the `GroupHeaderStyle` (of type `Style` with target type `DataGridGroupHeaderAppearance`).

* `AggregatesTextColor`&mdash;Defines the color for the aggregates part of the `GroupHeader`.
* `AggregatesTextFontAttributes`&mdash;Defines the font attributes for the aggregates part of the `GroupHeader`.
* `AggregatesTextFontFamily`&mdash;Defines the font family of the aggregates part of the `GroupHeader`.
* `AggregatesTextFontSize`&mdash;Defines the size of the aggregates part of the `GroupHeader`.
* `AggregatesTextMargin`&mdash;Defines the margin for the aggregates part of the `GroupHeader`.

Use the following properties to style and customzie the aggregate results when the `GroupAggregatesAlignment` is set to `NextToHeader`:

* `GroupAggregateCellStyle` (of type `Style` with target type `DataGridGroupAggregateCellAppearance`)&mdash;
* `GroupAggregateCellStyleSelector` (`IStyleSelector`)&mdash;
* `GroupAggregateCellTemplate` (`DataTemplate`)&mdash;Defines the appearance of each aggregate within the group header of the grid.

The following example shows how to define the `GroupHeaderStyle` in the page's resources:

<snippet id='ddatagrid-group-header-aggregate-styling-example'/>

>important For DataGrid `GroupHeader` Aggregates example refer to the [SDKBrowser Demo application]({%slug sdkbrowser-app%}) and navigate to the **DataGrid > Aggregates** category.

## Styling the Group Footer

The DataGrid provides the following options for styling its group footer:

* `GroupFooterStyle` (of type `Style` with target type `DataGridColumnFooterAppearance`)&mdash;Defines the style of the `GroupFooter` and the aggregates inside the footer.
* `GroupFooterStyleSelector` (`IStyleSelector`)&mdash;Defines the style of the selected `GroupFooter` by passing the `GroupFooterContext` in the selector.
* `FooterStyle` (of type `Style` with target type `DataGridColumnFooterAppearance`)&mdash;Defines the style of the Column Footer and the aggregates inside the Column Footer.

> To visualize the `GroupFooter`, set the `ShowGroupFooters` property to `True`. The property is a property inside the `RadDataGrid` instance.

The following example shows how to define the `GroupFooterStyle` in XAML:

<snippet id='datagrid-group-aggregate-styling-example'/>

The following example shows how to use the `GroupFooterStyleSelector` property:

**1.** Define the class to which the `GroupFooterContext` will be passed.

<snippet id='datagrid-group-aggregate-style-selector'/>

**2.** Define the style selector which will passed to the DataGrid in XAML.

<snippet id='datagrid-group-aggregate-style-selector-xaml'/>

>important For DataGrid `GroupFooter` Aggregates styling example refer to the [SDKBrowser Demo application]({%slug sdkbrowser-app%}) and navigate to the **DataGrid > Aggregates** category.

## Customizing the Group Footer Appearance

Customizing the footer in the DataGrid also changes the appearance of the aggregates inside the component.

The following example demonstrates how to change the style of the column footer aggregates:

**1.** Define the footer style in XAML.

<snippet id='datagrid-column-aggregate-styling-example'/>

**2.** Add the styling to the DataGrid.

<snippet id='datagrid-aggregate-styling-example'/>

> The footer style is added per column.

The following image shows the end result.

![Group Aggregate Style](../images/datagrid-grouping-aggregates.png)

>important For DataGrid `GroupFooter` styling example refer to the [SDKBrowser Demo application]({%slug sdkbrowser-app%}) and navigate to the **DataGrid > Aggregates** category.


## See Also

- [Property Aggregate Descriptor]({%slug datagrid-property-aggregate-descriptor%})
- [Delegate Aggregate Descriptor]({%slug datagrid-delegate-aggregate-descriptor%})
