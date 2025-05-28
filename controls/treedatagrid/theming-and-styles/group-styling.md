---
title: Group Header Styling
page_title: .NET MAUI DataGrid Documentation - Group Header Styling
description: Learn how to style the Group Headers in a grouped DataGrid control.
position: 2
slug: datagrid-group-header-styling
---

# Group Header Styling for .NET MAUI DataGrid

The [Telerik UI for .NET MAUI DataGrid]({%slug datagrid-overview%}) provides a `GroupHeaderStyle` property which defines the appearance of the group headers when the data is grouped.

>To learn more about the grouping functionality of the DataGrid, see the [Grouping Overview]({%slug datagrid-grouping-overview%}) topic.

## Group Header Properties

The `GroupHeaderStyle` property is of type `Style` and targets the `DataGridGroupHeaderAppearance` class. The `DataGridGroupHeaderAppearance` provides the following styling properties:

* `TextColor`(`Color`)&mdash;Defines the color for the text part of the group header.
* `SearchMatchTextColor`(`Color`)&mdash;Defines the color that is used for the parts of the group header's text that are search matches. For more details on this, see the [Search as You Type]({%slug datagrid-search-as-you-type%}) topic.
* `AggregatesTextColor`(`Color`)&mdash;Defines the color for the aggregates part of the group header. For more details on this, see the [Aggregates]({%slug datagrid-aggregates%}) topic.
* `BackgroundColor`(`Color`)&mdash;Defines the color that fills the area within the header of the DataGrid group header.
* `SearchMatchBackgroundColor`(`Color`)&mdash;Defines the color that fills the area within the border when the cell contains a search-match. For more details on this, see the [Search as You Type]({%slug datagrid-search-as-you-type%}) topic.
* `GroupLevelIndentation`(`double`)&mdash;Defines the indentation that accumulates for each group level.
* `BorderColor`(`Color`)&mdash;Defines the color that fills the border region of the group header.
* `BorderThickness`(`Thickness`)&mdash;Defines the thickness of the border.
* `TextMargin`(`Thickness`)&mdash;Defines the margin for the text part of the group header.
* `VerticalTextAlignment`(`TextAlignment`)&mdash;Defines the vertical text alignment.
* `HorizontalTextAlignment`(`TextAlignment`)&mdash;Defines the horizontal text alignment.
* `TextFontattributes`(`FontAttributes`)&mdash;Defines the font attributes of the group header's text part.
* `TextFontFamily`(`string`)&mdash;Defines the font family of the group header's text part.
* `TextFontSize`(`double`)&mdash;Define the font size of the group header's text part.
* `AggregatesTextMargin`(`Thickness`)&mdash;Defnes the margin for the aggregates part of the group header. For more details on this, see the [Aggregates]({%slug datagrid-aggregates%}) topic.
* `AggregatesTextFontAttributes`(`FontAttributes`)&mdash;Defines the font attributes for the aggregates part of the group header.
* `AggregatesTextFontFamily`(`string`)&mdash;Defines the font family for the aggregates part of the group header.
* `AggregatesTextFontSize`(`double`)&mdash;Define the font size for the aggregates part of the group header.

## Group Header Button Properties

By default, the Button of the group header uses an internal symbol font family. To render text instead of a symbol when the button is expanded or collapsed, set a font family to the `ButtonFontFamily` property and add the text to the `ExpandButtonText` and `CollapseButtonText` properties.

* `ButtonFontAttributes`(`FontAttributes`)&mdash;;Defines the font attributes of the expand and collapse symbol.
* `ButtonFontFamily`(`string`)&mdash;Defines the font family of the expand and collapse symbol.
* `ButtonFontSize`(`double`) options&mdash;Defines the font size of the expand and collapse symbol.
* `ButtonMargin`(`Thickness`)&mdash;Defines the margin of the expand and collapse symbol.
* `ButtonTextColor`(`Color`)&mdash;Defines the text color of the expand and collapse symbol.
* `CollapseButtonText`(`string`)&mdash;Defines the text for the collapse state of the group header.
* `ExpandButtonText`(`string`)&mdash;Defines the text for the expand state of the group header.

The following example demonstrates how to apply a sample `GroupHeaderStyle` to the DataGrid:

**1.** Add a sample `Style` with `TargetType` set to `DataGridGroupHeaderAppearance` to the page's resources:

<snippet id='datagrid-groupheader-styling-style' />

**2.** Add the DataGrid definition to the page with its `GroupHeaderStyle` applied:

<snippet id='datagrid-groupheader-styling-xaml' />

**3.** Add the `ViewModel` class:

<snippet id='datagrid-grouping-viewmodel' />

**4.** Add the data item used for binding the DataGrid:

<snippet id='datagrid-grouping-object' />

**5.** Set the binding context of the DataGrid to the `ViewModel` class:

<snippet id='datagrid-grouping-propertygroupdescriptor-setvm' />

Check the result at the image below:

![Telerik .NET MAUI DataGrid Group Header Style](../images/datagrid-grouping-groupheaderstyle.png)

## See Also

* [Grouping Overview]({%slug datagrid-grouping-overview%})
* [Search as You Type]({%slug datagrid-search-as-you-type%})
* [Aggregates]({%slug datagrid-aggregates%})
