---
title: NavigationView Styling
page_title: .NET MAUI NavigationView Documentation - NavigationView Styling
description: Learn how to style the header and toggle button of the NavigationView control for .NET MAUI. 
position: 0
slug: navigationview-styling
---

# .NET MAUI NavigationView Styling

The NavigationView Header for .NET MAUI provides a styling mechanism for customizing its look and the look of the toggle navigation button.
To use it, set the `HeaderStyle` property of the control with a target type `NavigationViewHeader`.

The available properties are described in the table below:

| Property | Description |
| -------- | ----------- |
| `FontFamily` (`string`) | Specifies the font family of the container in compact mode. |
| `FontSize` (`double`) | Specifies the font size in pixels of the displayed text. |
| `FontAttributes` (`Microsoft.Maui.Control.FontAttributes`) | Specifies the font attributes of the displayed text |
| `TextDecorations` (`Microsoft.Maui.TextDecorations`) | Specifies the text decorations of the displayed text. |
| `LineBreakMode` (`Microsoft.Maui.LineBreakMode`) | Specifies the line break mode of the displayed text. |
| `HorizontalTextAlignment` (`Microsoft.Maui.TextAlignment`) | Specifies the horizontal alignment of the displayed text. |
| `VerticalTextAlignment` (`Microsoft.Maui.TextAlignment`) | Specifies the vertical alignment of the displayed text. |
| `HorizontalContentOptions` (`Microsoft.Maui.Controls.LayoutOptions`) | Specifies the horizontal alignment of the header text. |
| `VerticalContentOptions` (`Microsoft.Maui.Controls.LayoutOptions`) | Specifies the vertical alignment of the header text. |
| `BackgroundColor` (`Color`) | Specifies the background color of the header area. |
| `BorderColor` (`Color`) | Specifies the border color around the header area. |
| `BorderBrush` (`Brush`) | Specifies the border brush around the header area. |
| `BorderThickness` (`Thickness`) | Specifies the border thickness around the header area. |
| `CornerRadius` (`Thickness`) | Specifies the corner radius of the border around the header area. |
| `ContentPadding` (`Thickness`) | Specifies the content padding of the header area. |
| `CompactWidth` | Specifies the width of the container in compact mode. |
| `ExpandedWidth` | Specifies the width of the container in expanded mode. |
| `IsHeaderButtonVisible` (`bool`) Default value `true` | Specifies the visibility of the navigation toggle button. |
| `IsHeaderButtonToggled` (`bool`) | Specifies whether the navigation button is toggled. |
| `HeaderButtonStyle` (`Style` with a target type of `NavigationViewToggleButton`) | Specifies the style that will be applied to the navigation toggle button. |

## Styling the Navigation Toggle Button 

You can style the toggle button by setting the `HeaderButtonStyle` property to the `HeaderStyle`. Thy target type of the `HeaderButtonStyle` is `NavigationViewToggleButton`.

`NavigationViewToggleButton` inherits from [Telerik .NET MAUI Button]({%slug button-overview%}) control. Use all properties applicable for `RadButton` to style the toggle button.

### Visual States

You can customize the visual states to the `NavigationViewToggleButton`. Here is a sample XAML definition with visual states:

<snippet id='navigationview-togglebutton-styling' />

## Styling the Overlay

You can display an overlay when Pane opens by setting the `IsDismissOverlayVisible` (`bool`) property. The default value is `false`. 

You can style the overlay by using the following properties:


* `DismissOverlayBrush` (`Brush`)&mdash;Specifies the brush for the overlay.
Set a color for the overlay by using the `DismissOverlayColor` (`Color`)&mdash;


## See Also

- [.NET MAUI NavigationView Forum Page](https://www.telerik.com/forums/maui?tagId=1978)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
