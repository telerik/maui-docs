---
title: Commands
page_title: .NET MAUI Toolbar Documentation - Commands
description: "Reviwe all Configuration options Telerik .NET MAUI Toolbar provides."
position: 10
slug: toolbar-commands
---

# .NET MAUI Toolbar Commands

This article describes all available commands in the .NET MAUI Toolbar control.

* `NavigateCommand`(`ICommand`)&mdash;Gets a command for navigating to the next level of the toolbar hierarchy. The command accepts a collection of `Telerik.Maui.Controls.ToolbarItems` as a parameter.
* `NavigateBackCommand`(`ICommand`)&mdash;Gets a command for navigating back to the previous level of the toolbar hierarchy. The previous `Telerik.Maui.Controls.ToolbarItems` stored in the navigation stack from the last invocation of the `Telerik.Maui.Controls.RadToolbar.NavigateCommand` are restored in the toolbar.
* `ScrollForwardCommand`(`ICommand`)&mdash;Gets a command for scrolling the contents of the toolbar in forward direction. This command is applicable when the `RadToolbar.OverflowMode` is set to `Scroll`.
* `ScrollBackwardCommand`(`ICommand`)&mdash;Gets a command for scrolling the contents of the toolbar in backward direction. This command is applicable when the `RadToolbar.OverflowMode` is set to Scroll.

## See Also

- [Toolbar Items]({%slug toolbar-items%})
- [Styling]({%slug toolbar-styling%})
