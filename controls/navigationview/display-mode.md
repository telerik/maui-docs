---
title: Display Mode
page_title: .NET MAUI NavigationView Documentation - Display Mode
description: Learn what are the different options to display the navigation pane in your .NET MAUI applications.
position: 3
slug: navigationview-display-mode
---

# .NET MAUI NavigationView Display Mode

The NavigationView provides three layouts based on its `DisplayMode` (enum of type `Telerik.Maui.Controls.NavigationViewDisplayMode`) property. The available options are:

* `Minimal`&mdash;This option fixes the menu button. The pane shows and hides when the menu button is clicked.
* `Compact`&mdash;The pane always shows as a narrow sliver which can be opened to full width.
* `Expanded`&mdash;The pane stays open alongside the content.

## Auto-changing the Display Mode

The NavigationView dynamically adjusts its layout depending on its size. This is controlled with the `AutoChangeDisplayMode` (`bool`) property. On desktop its value is `true`, on mobile `false`.

In addition use the following porperties for setting the minimum width at which the NavigationView enters the `Compact` and `Expanded` display modes: 

* `ExpandedModeThresholdWidth` (`double`)&mdash;Specifies the minimum width at which the NavigationView enters Expanded display mode.
* `CompactModeThresholdWidth` (`double`)&mdash;Specifies the minimum width at which the NavigationView enters Compact display mode.

## See Also

- [.NET MAUI NavigationView Forum Page](https://www.telerik.com/forums/maui?tagId=1978)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
