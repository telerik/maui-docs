---
title: Content Styling
page_title: .NET MAUI TabView Documentation - Content Styling
description: Learn how to style the Telerik UI for .NET MAUI TabView Content by setting border thickness, color and corner radius.
slug: tabview-content-styling
tags: tabview, content, style, maui, dotnet
position: 4
---

# .NET MAUI TabView Content Styling

TabView's `ContentStyle` property allows you to style the content area. `TabViewContent` provides the following properties:

* `BackgroundColor` (`Color`)&mdash;Specifies the background color of the content.
* `BorderColor` (`Color`)&mdash;Specifies the border color of the content.
* `BorderThickness` (`Thickness`)&mdash;Specifies the border thickness of the content.
* `CornerRadius` (`Thickness`)&mdash;Specifies the corner radius of the content.
* `ContentPadding` (`Thickness`)&mdash;Specifies the padding of the inner content of the content.

<snippet id='tabview-styling-contentstyle' />

The image below shows TabView after applying `ContentStyle`:

![.NET MAUI TabView Content Style](images/styling-contentstyle.png)

> For a runnable example with the TabView `ContentStyle` scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **TabView > Styling**.

## See Also

- [Styling the Header]({%slug tabview-header-styling%})
- [Styling the Header Item]({%slug tabview-header-item-styling%})
- [Applying a StyleSelector to the Header Item]({%slug tabview-header-itemstyle-selector%})
