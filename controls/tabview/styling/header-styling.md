---
title: Header Styling
page_title: .NET MAUI TabView Documentation - Header Styling
description: Learn how to style to the Telerik UI for .NET MAUI TabView header element.
slug: tabview-header-styling
tags: tabview, header, styling
position: 1
---

# .NET MAUI TabView Header Styling

Through `HeaderStyle` property of the .NET MAUI TabView you can modify the `TabViewHeader`. The properties `TabViewHeader` provides are described in the table below:

| Property | Description |
| -------- | ---------- |
| `BackgroundColor` (`Color`) | Specifies the background color of the header area. |
| `BorderColor` (`Color`) | Specifies the border color of the header area. |
| `BorderThickness` (`Thickness`) | Specifies the border thickness of the header area. |
| `CornerRadius` (`Thickness`) | Specifies the corner radius of the header area. |
| `ContentPadding` (`Thickness`) | Specifies the padding of the inner content of the header area. |
| `Spacing` (`double`) | Specifies the spacing in pixels between the header items in the header area. |
| `SelectedIndex` (`int`) | Specifies the index of the currently selected item in the header area. |
| `IsScrollable` (`bool`) | Specifies whether the header area can be scrolled with pan gesture. |
| `Orientation` (`enum` of type `Telerik.Maui.Controls.TabViewScrollOrientation`) | Specifies the scroll orientation of the header area. The available options are `Horizontal` and `Vertical`. |

Check below a quick example:

<snippet id='tabview-styling-headerstyle' />

And the result is the following:

![.NET MAUI TabView Header Style](images/styling-headerstyle.png)

> For a runnable example with the TabView `HeaderStyle` scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **TabView > Styling**.

## See Also

- [Styling the Header]({%slug tabview-header-styling%})
- [Styling the Header Item]({%slug tabview-header-item-styling%})
- [Applying a StyleSelector to the Header Item]({%slug tabview-header-itemstyle-selector%})
- [Styling the TabView Content]({%slug tabview-content-styling%})
