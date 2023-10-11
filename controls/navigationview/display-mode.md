---
title: Display Mode
page_title: .NET MAUI NavigationView Documentation - Display Mode
description: Learn what are the different options to display the navigation pane in your .NET MAUI applications.
position: 3
slug: navigationview-display-mode
---

# .NET MAUI NavigationView Display Mode

The Telerik UI for .NET MAUI NavigationView allows you to set different display options to display the navigation pane by setting the `DisplayMode` (enum of type `Telerik.Maui.Controls.NavigationViewDisplayMode`) property. The values for `DisplayMode` are:

* `Minimal`&mdash;This option fixes the menu button. The pane shows and hides when the menu button is clicked.
* Default `Compact`&mdash;The pane always shows as a narrow sliver which can be opened to full width.
* `Expanded`&mdash;The pane stays open alongside the content.

## Auto-changing the Display Mode

You can enable the NavigationView to auto-change the display mode depending on the widths of the `ExpandedModeThresholdWidth` and `CompactModeThresholdWidth` by using the `AutoChangeDisplayMode` (`bool`) property. The default value on mobile is `false`, and on desktop is `true`. 

* `ExpandedModeThresholdWidth` (`double`)&mdash;Specifies the minimum width at which the NavigationView enters Expanded display mode.
* `CompactModeThresholdWidth` (`double`)&mdash;Specifies the minimum width at which the NavigationView enters Compact display mode.

## See Also

- [.NET MAUI NavigationView Forum Page](https://www.telerik.com/forums/maui?tagId=1978)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
