---
title: Commands
page_title: .NET MAUI TreeView Documentation - Commands
description: Check our &quot;Commands&quot; documentation article for Telerik TreeView for .NET MAUI control.
position: 8
slug: treeview-commands
---

# Commands

This article explains all commands that Treeview for .NET MAUI provides.

## Commands for expanding and collapsing items

TreeView exposes the following commands for expanding and collapsing all items:

* `ExpandAllCommand`(`ICommand`)&mdash;Gets a command to expand all items in the control.
* `CollapseAllCommand`(`ICommand`)&mdash;Gets a command to collapse all items in the control.

<snippet id='treeview-expand-collapse-commands'/>

>important For the Treeview Expand Collapse Commands example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) TreeView -> Commands category.

## Commands for checking and unchecking items

And the following commands for checking and unchecking all items:

* `CheckAllCommand`(`ICommand`)&mdash;Gets a command to check all items in the control.
* `UncheckAllCommand`(`ICommand`)&mdash;Gets a command to uncheck all items in the control.

<snippet id='treeview-check-uncheck-commands'/>

>important For the Treeview Check Uncheck Commands example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) TreeView -> Commands category.


## Scrolling commands

* `ScrollToCommand`(`ICommand`)&mdash;Gets a command that scrolls to an item in the control, which is specified as a parameter.

## See Also

* [Expand/Collapse]({%slug treeview-expand-collapse%})
* [CheckBoxes]({%slug treeview-checkboxes%})
* [Theming]({%slug treeview-item-style%})