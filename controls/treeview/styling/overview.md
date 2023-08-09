---
title: Overview
page_title: .NET MAUI TreeView Documentation - Item Style
description: The TreeView for .NET MAUI allows you to easily style its look.
position: 0
slug: treeview-style-overview
---

# Styling the TreeView

The TreeView for .NET MAUI allows you to style its look by using the following properties:

* `BackgroundColor`(`Color`)&mdash;Specifies the background color of the control.
* `BorderColor`(`Color`)&mdash;Specifies the border color of the control.
* `BorderBrush`(`Color`)&mdash;Specifies the border brush of the control.
* `BorderThickness`(`Thickness`)&mdash;Specifies the border thickness of the control.
* `CornerRadius`(`Thickness`)&mdash;Specifies the corner radius of the control.
* `ContentPadding`(`Thickness`)&mdash;Specifies the content padding of the control.

## Style the Empty Template

When no data is displayed in the control, an empty template is visualized. Style the template by using the `EmptyStyle` property: 

* `EmptyStyle`(`Style` with target type `telerik:ItemsEmptyView`)&mdash;Specifies the style applied to the empty view.

You can use the following properties: 

    * `VerticalContentOptions` (of type `LayoutOptions`)&mdash;Specifies the vertical layout options of the displayed content.
    * `HorizontalContentOptions` (of type `LayoutOptions`)&mdash;Specifies the horizontal layout options of the displayed content.
    * `ContentTemplate` (`DataTemplate`)&mdash;Specifies the content template of the empty view.

To customize the empty view, use the `EmptyTemplate` (`DataTemplate`) property. 

## See Also

* [Expand and Collapse TreeView Items]({%slug treeview-expand-collapse%})
* [CheckBoxes in TreeView]({%slug treeview-checkboxes%})
* [Styling the TreeView Item]({%slug treeview-item-style%})
* [Scrolling options]({%slug treeview-scrolling%})
* [Multiple and Single Selection]({%slug treeview-selection%})
* [Events]({%slug treeview-events%})
* [Available Commands in .NET MAUI TreeView]({%slug treeview-commands%})