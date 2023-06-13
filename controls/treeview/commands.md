---
title: Commands
page_title: .NET MAUI TreeView Documentation - Commands
description: The .NET MAUI TreeView provides various commands that allow you to initiate expand or collapse actions, check and uncheck actions, and to scroll to a specific item.
position: 8
slug: treeview-commands
---

# Commands

The .NET MAUI TreeView provides various commands that allow you to initiate expand or collapse actions, check and uncheck actions, and to scroll to a specific item.

## Expanding and Collapsing Items

TreeView exposes the following commands for expanding and collapsing all items:

* `ExpandAllCommand`(`ICommand`)&mdash;Gets a command to expand all items in the control.
* `CollapseAllCommand`(`ICommand`)&mdash;Gets a command to collapse all items in the control.

<snippet id='treeview-expand-collapse-commands'/>

> For a runnable example demonstrating the TreeView Expand and Collapse commands, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **TreeView > Commands**.
## Checking and Unchecking Items

TreeView exposes the following commands for checking and unchecking all items:

* `CheckAllCommand`(`ICommand`)&mdash;Gets a command to check all items in the control.
* `UncheckAllCommand`(`ICommand`)&mdash;Gets a command to uncheck all items in the control.

<snippet id='treeview-check-uncheck-commands'/>

> For a runnable example demonstrating the TreeView Check and Uncheck commands, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **TreeView > Commands**.

## Scrolling

TreeView exposes the following command that allows you to control the scrolling within the component:

* `ScrollToCommand`(`ICommand`)&mdash;Gets a command that scrolls to an item in the control, which is specified as a parameter.

## See Also

* [Expand/Collapse]({%slug treeview-expand-collapse%})
* [CheckBoxes]({%slug treeview-checkboxes%})
* [Theming]({%slug treeview-item-style%})