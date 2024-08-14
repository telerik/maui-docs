---
title: Disabling Keyboard Functionality in DataGrid for MAUI
description: Learn how to disable keyboard navigation in DataGrid for MAUI to prevent automatic row or cell selection when using arrow keys.
type: how-to
page_title: How to Disable Keyboard Navigation in DataGrid for MAUI
slug: disable-keyboard-functionality-datagrid-maui
tags: datagrid, maui, keyboard, navigation, disable
res_type: kb
---

## Environment

| Product | Version |
| --- | --- |
| DataGrid for MAUI | 7.1.0 |

## Description

I want to disable the keyboard functionality for the `RadDataGrid` to prevent automatic selection of the next row or cell when arrow keys are pressed. I plan to manage this behavior manually.

This KB article also answers the following questions:
- How can I stop the DataGrid in MAUI from responding to keyboard inputs?
- What approach can I use to disable arrow key navigation in DataGrid for MAUI?
- Is it possible to manually control cell or row selection in DataGrid for MAUI without using the keyboard?

## Solution

To disable the keyboard functionality in the `RadDataGrid`, implement a custom `KeyDownCommand` that overrides the default keyboard behavior. By setting the `CanExecute` method to return `false`, keyboard input is effectively ignored, thus disabling the default navigation and selection behavior. Here's how to implement and use the custom command:

**1.** Define the `KeyDownCommand` class:

```csharp
public class KeyDownCommand : DataGridCommand
{
    public KeyDownCommand()
    {
        Id = DataGridCommandId.KeyDown;
    }
    public override bool CanExecute(object parameter)
    {
        // return false; if you want to stop executing the command at all.
        // return true; and then inside the Execute method, white custom logic
        return false;
    }
    public override void Execute(object parameter)
    {
        // uncomment the line below in order to execute the default command and enable the keyboard navigation support or you can write custom logic implementation.
        //this.Owner.CommandService.ExecuteDefaultCommand(DataGridCommandId.KeyDown, parameter);
    }
}

```

**2.** Add the custom command to the RadDataGrid's `Commands` collection:

```csharp
this.datagrid.Commands.Add(new KeyDownCommand());
```

By following these steps, the keyboard functionality of the `RadDataGrid` will be disabled, and it will no longer respond to arrow keys for navigation and selection.

For more information on commands in `RadDataGrid` for MAUI, refer to the official Telerik documentation on [DataGrid Commands]({%slug datagrid-commands-overview%}).
