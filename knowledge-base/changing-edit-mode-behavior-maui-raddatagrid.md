---
title: Changing Edit Mode Behavior in DataGrid for MAUI
description: Learn how to modify the edit mode behavior in RadDataGrid for MAUI to enter edit mode with a single click instead of a double-click.
type: how-to
page_title: Changing Edit Mode Behavior in RadDataGrid for MAUI
slug: changing-edit-mode-behavior-maui-raddatagrid
tags: maui, raddatagrid, edit mode, cell tap, cell double tap
res_type: kb
---
## Environment
| Property | Value |
|---|---|
| Product | DataGrid for MAUI |
| Version | 6.7.0 |

## Description
I want to modify the behavior of the RadDataGrid in my .NET Maui application so that it enters edit mode with a single click instead of requiring a double-click.

## Solution
To achieve this, you can use a custom `CellTap` command called `CellTapUserCommand`. Here's an example of how to implement it:

```csharp
public class CellTapUserCommand : DataGridCommand
{
    public CellTapUserCommand()
    { 
        Id = DataGridCommandId.CellTap;
    }

    public override bool CanExecute(object parameter)
    {
        return true;
    }

    public override void Execute(object parameter)
    {
        if (parameter is not DataGridCellInfo cellInfo)
        {
            return;
        }
        
        this.Owner.CommandService.ExecuteDefaultCommand(DataGridCommandId.CellDoubleTap, parameter);
    }
}
```

To apply the `CellTapUserCommand` to your RadDataGrid, add it to the `Commands` collection:

```csharp
this.dataGrid.Commands.Add(new CellTapUserCommand());
```

By utilizing this custom command, you can now enter edit mode with a single click on a cell in the RadDataGrid.

## See Also

- [DataGrid for .NET MAUI Documentation](https://docs.telerik.com/devtools/maui/controls/datagrid/overview)
- [DataGrid Commands](https://docs.telerik.com/devtools/maui/controls/datagrid/commands/overview)
