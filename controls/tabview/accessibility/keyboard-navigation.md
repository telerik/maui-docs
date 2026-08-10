---
title: Keyboard Navigation
meta_title: .NET MAUI TabView Documentation - Keyboard Support
description: Learn more about the available keyboard combinations as part of the supported Telerik UI for .NET MAUI TabView accessibility standards.
position: 1
slug: tabview-keyboard-support
---

# .NET MAUI TabView Keyboard Navigation Support on Desktop

The [Telerik UI for .NET MAUI TabView]({%slug tabview-overview%}) provides keyboard navigation support on WinUI and MacCatalyst.

The table below lists the available keyboard combinations and their corresponding actions:

| Hotkey | Action |
| ------ | ------ |
| `Tab` | Enters or exits the TabView and focuses the selected tab (if selection is set&mdash; by default the first tab is selected). |
| `Left Arrow` | Navigates to the previous tab in the TabView. |
| `Right Arrow` | Navigates to the next tab in the TabView. |
| `Down Arrow` | Navigates to the next tab in the TabView&mdash;in vertical orientation. |
| `Up Arrow` | Navigates to the previous tab in the TabView&mdash;in vertical orientation. |
| `Enter` | Selects the currently focused tab. |
| `Space` | Selects the currently focused tab. |

Here is how the keyboard navigation support looks on WinUI:

![.NET MAUI TabView Keyboard Navigation Support](../images/tabview-keyboard-navigation-support.gif)

## Setting CurrentItem

The TabView allows you to use the `CurrentItem` property of type `object` to programmatically modify the current item during keyboard navigation.

## See Also

- [TabViewItem]({%slug tabview-item%})
- [Styling]({%slug tabview-styling%})
- [Templates]({%slug tabview-templates%})