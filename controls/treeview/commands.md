---
title: Commands
page_title: .NET MAUI TreeView Documentation - Commands
description: The .NET MAUI TreeView provides various commands that allow you to initiate expand or collapse actions, check and uncheck actions, and to scroll to a specific item.
position: 8
slug: treeview-commands
---

# Commands

The .NET MAUI TreeView provides various commands that allow you to initiate expand or collapse actions, check and uncheck actions, scroll to a specific item and more. The table below lists all available commands:

| Commands | Description |
| -------- | ---------- |
| `ExpandAllCommand` (`ICommand`) | Gets a command to expand all items in the control. |
| `ExpandCommand` (`ICommand`) | Gets a command to expand a specific item in the control. |
| `CollapseAllCommand` (`ICommand`) | Gets a command to collapse all items in the control. |
| `CollapseCommand` (`ICommand`) | Gets a command to collapse a specific item in the control. |
| `CheckAllCommand` (`ICommand`) | Gets a command to check all items in the control. |
| `CheckCommand` (`ICommand`) | Gets a command to check a specific item in the control. |
| `UncheckAllCommand` (`ICommand`) | Gets a command to uncheck all items in the control. |
| `UncheckCommand` (`ICommand`) | Gets a command to uncheck a specific item in the control. |
| `ScrollToCommand` (`ICommand`) | Gets a command to uncheck all items in the control. |
| `ItemExpandedCommand` (`ICommand`) | Defines a command to execute when an item is expanded after a user interaction. The command should accept a single parameter with the expanded item. |
| `ItemCollapsedCommand` (`ICommand`) | Defines a command to execute when an item is collapsed after a user interaction. The command should accept a single parameter with the collapsed item. |
| `ItemCheckedCommand` (`ICommand`) | Defines a command to execute when an item is checked after a user interaction. The command should accept a single parameter with the checked item. |
| `ItemUncheckedCommand` (`ICommand`) | Defines a command to execute when an item is unchecked after a user interaction. The command should accept a single parameter with the unchecked item. |
| `LoadChildrenOnDemandCommand` (`ICommand`) | Defines a command to execute when loading an item on demand. The command accepts a single parameter of type `Telerik.Maui.Controls.TreeView.TreeViewLoadChildrenOnDemandCommandContext`. |
| `ItemTappedCommand` (`ICommand`) | Defines a command to execute when an item is tapped. The command accepts a single parameter with the item being tapped. |
| `ItemHoldingCommand` (`ICommand`) | Defines a command to execute when an item is held. The command accepts a single parameter with the item being held. |


## Using the ExpandAll and CollapseAll Commands

The following TreeView definition shows how to use the expand and collapse commands.

<snippet id='treeview-expand-collapse-commands'/>

![.NET MAUI TreeView Expand and Collapse](images/treeview-expand-collapse.gif)

> For a runnable example demonstrating the TreeView Expand and Collapse commands, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **TreeView > Commands**.

## Using the CheckAll and UncheckAll Commands

The following TreeView definition shows how to use the check and uncheck commands.

<snippet id='treeview-check-uncheck-commands'/>

![.NET MAUI TreeView Check and Uncheck](images/treeview-check-uncheck-items.gif)

> For a runnable example demonstrating the TreeView Check and Uncheck commands, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **TreeView > Commands**.

## See Also

* [Expand and Collapse TreeView Items]({%slug treeview-expand-collapse%})
* [CheckBoxes in TreeView]({%slug treeview-checkboxes%})
* [Styling the TreeView Item]({%slug treeview-item-style%})
* [Scrolling options]({%slug treeview-scrolling%})
* [Multiple and Single Selection]({%slug treeview-selection%})
* [Events]({%slug treeview-events%})
