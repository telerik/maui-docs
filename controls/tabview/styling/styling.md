---
title: Styling
page_title: .NET MAUI TabView Documentation - Styling
description: Review the styling options for the Telerik for .NET MAUI TabView.
slug: tabview-styling
previous_url: /controls/tabview/styling
tags: tabview, styling, maui, dotnet
position: 0
---

# .NET MAUI TabView Styling

The .NET MAUI TabView provides means for modifying its visual appearance so that it matches the style of the app.  You can style different parts of the TabView—its header, items, and content area. 

> Check the [TabView Visual Structure]({%slug tabview-visual-structure%}) topic for a visual representation of the TabView elements.

You can use any of the following TabView properties to change its look&amp;feel:

* `BackgroundColor` (`Color`)&mdash;Specifies the background color of the control.
* `BorderColor` (`Color`)&mdash;Specifies the border color of the control.
* `BorderThickness` (`Thickness`)&mdash;Specifies the border thickness of the control.
* `CornerRadius` (`Thickness`)&mdash;Specifies the corner radius of the control.
* `ContentPadding` (`Thickness`)&mdash;Specifies the padding of the inner content of the control.

In addition, TabView provides the listed below styling properties for modifying its elements - header, TabView items and content area.

* [`HeaderStyle`]({%slug tabview-header-styling%})&mdash;Specifies the style of the entire header area (border, background color etc.);
* [`HeaderItemStyle`]({%slug tabview-header-item-styling%}) (`Style` with target type `TabViewHeaderItem`)&mdash;Specifies the style selector that chooses the style for the header items (font, text color etc.)
* [`HeaderItemStyleSelector`]({%slug tabview-header-itemstyle-selector%})&mdash;Specifies the style of the individual header items (font, text color etc.). This property has a higher precedence than the `HeaderItemStyle` property.
* [`ContentStyle`]({%slug tabview-content-styling%})&mdash;Specifies the style of the entire content area (borders, background color etc.);

## See Also

- [Styling the Header]({%slug tabview-header-styling%})
- [Styling the Header Item]({%slug tabview-header-item-styling%})
- [Applying a StyleSelector to the Header Item]({%slug tabview-header-itemstyle-selector%})
- [Styling the TabView Content]({%slug tabview-content-styling%})
