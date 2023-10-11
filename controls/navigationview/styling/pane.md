---
title: Pane Styling
page_title: .NET MAUI NavigationView Documentation - Pane Styling
description: Learn how to style the header and footer of the navigation pane in the .NET MAUI NavigationView control.
position: 1
slug: navigationview-pane-styling
---

# .NET MAUI NavigationView Pane Styling

The NavigationView Pane for .NET MAUI provides a styling mechanism for customizing its look, also the look of its header and footer.
To use it, set the `PaneStyle` property of the control with a target type `NavigationViewPane`.

The available properties are described in the table below:

| Property | Description |
| -------- | ----------- |
| `ItemSpacing` (`double`) | Description |
| `DisplayMode` (enum of type `Telerik.Maui.Controls.NavigationViewDisplayMode`) | Specifies how the pane displays the navigation items - `Minimal`, `Compact` or `Expanded`. |
| `IsOpen` (`bool`) | Specifies whether the navigation pane is open. |
| `CompactWidth` (`double`) | Specifies the width of the navigation pane in compact mode. |
| `ExpandedWidth` (`double`) | Specifies the width of the navigation pane in expanded mode. |
| `HeaderStyle` (`Style` with a target type of `NavigationViewPaneHeader`) | Specifies the style applied to the Pane header. |
| `HeaderTemplate` (`ControlTemplate`) | Replaces the default header template with a custom template. |
| `FooterStyle` (`Style` with a target type of `NavigationViewPaneFooter`) | Specifies the style applied to the Pane header. |
| `FooterTemplate` (`ControlTemplate`) | Replaces the default header template with a custom template. |
| `VerticalScrollBarStyle` (`Style` with a target type of `RadScrollBar`) | Specifies the style for the vertical scroll bar. |
| `VerticalScrollBarTemplate` (`ControlTemplate`) | Specifies the template of the vertical scroll bar. |
| `VerticalScrollBarVisibility` (`Microsoft.Maui.ScrollBarVisibility`) | Specifies the visibility of the vertical scroll bar. The available options are - `Default`, `Always`, and `Never`. |
| `BackgroundColor` (`Color`) | Specifies the background color of the pane. |
| `BorderColor` (`Color`) | Specifies the border color of the pane. |
| `BorderBrush` (`Brush`) | Specifies the border brush of the pane. |
| `BorderThickness` (`Thickness`) | Specifies the border thickness of the pane. |
| `CornerRadius` (`Thickness`) | Specifies the corner radius of the border around the pane. |
| `ContentPadding` (`Thickness`) | Specifies the content padding of the control. |

## Styling the Pane Header and Footer 

You can style the pane header and footer by setting the `HeaderStyle` and `FooterStyle` properties to the `PaneStyle`.

You can use the following properties for `HeaderStyle` and `FooterStyle`:

| Property | Description |
| -------- | ----------- |
| `BackgroundColor` (`Color`) | Specifies the background color of the pane. |
| `BorderColor` (`Color`) | Specifies the border color of the pane. |
| `BorderBrush` (`Brush`) | Specifies the border brush of the pane. |
| `BorderThickness` (`Thickness`) | Specifies the border thickness of the pane. |
| `CornerRadius` (`Thickness`) | Specifies the corner radius of the border around the pane. |
| `ContentPadding` (`Thickness`) | Specifies the content padding of the control. |

## Templates

You can replace the default pane header and footer template with custom one by setting the `HeaderTemplate` (`ControlTemplate`) and `FooterTemplate` (`ControlTemplate`) to the `PaneStyle`.

## See Also

- [.NET MAUI NavigationView Forum Page](https://www.telerik.com/forums/maui?tagId=1978)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
