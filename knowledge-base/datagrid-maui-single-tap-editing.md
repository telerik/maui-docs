---
title: Enabling Single Tap Cell Editing in DataGrid for MAUI
description: Learn how to configure the DataGrid in MAUI to enter edit mode with a single tap or click on a cell.
type: how-to
page_title: How to Enable Single Tap Editing in a MAUI DataGrid
slug: datagrid-maui-single-tap-editing
tags: datagrid, maui, editing, celltap, cell, tap, single tap, command
res_type: kb
---

## Environment

| Product | Version |
| --- | --- |
| DataGrid for MAUI | 7.0.0 |

## Description

When using the DataGrid in MAUI, the default behavior requires users to double-tap (or double-click on desktop) a cell to enter edit mode. This article demonstrates how to modify this behavior to allow entering edit mode with a single tap or click on a cell, making the user interaction more intuitive.

This KB article also answers the following questions:
- How can I modify the DataGrid in MAUI to edit on single tap?
- Is there a workaround to enable single click editing in DataGrid for MAUI?
- How to customize cell tap actions in DataGrid for MAUI?

## Solution

To achieve single tap editing in the DataGrid, you need to handle the `CellTap` command and execute the default logic of a `CellDoubleTap` instead. Follow the steps below:

**1.** Define the DataGrid in your XAML file:

```xaml
<telerik:RadDataGrid x:Name="grid"/>
```

**2.** Create the custom command:

Implement the `CellTapUserCommand` by inheriting from `DataGridCommand`. In the `Execute` method, call the default command for cell double tap:

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
        this.Owner.CommandService.ExecuteDefaultCommand(DataGridCommandId.CellDoubleTap, parameter);
    }
}
```

**3.** Implement the logic in your page's code-behind:

First, create a simple data model if you haven't already:

```csharp
public class Data
{
    public int Id { get; set; }
    public string Name { get; set; }
}
```

Then, add data to the DataGrid ItemsSource and add the command to the DataGrid `Commands` collection:

```csharp
public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();

        var data = new ObservableCollection<Data>();

        for (int i = 0; i < 10; i++)
        {
            data.Add(new Data { Id = i, Name = "Name" + i});
        }

        this.grid.ItemsSource = data;
        this.grid.Commands.Add(new CellTapUserCommand());
    }
}
```


With this setup, the DataGrid will enter edit mode with a single tap or click on a cell. The cell's updated value will be committed when it exits edit mode, such as when clicking outside the entry.

## Notes

- Custom commands in DataGrid allow for a high degree of interaction customization, making it easier to tailor the user experience to specific requirements.
- Ensure that the `CellTap` command does not conflict with other custom logic you may have implemented related to cell tapping.

## See Also

- [DataGrid Commands Overview]({%slug datagrid-commands-overview%})
- [DataGrid CellTap Command Documentation]({%slug datagrid-commands-cell-tap%})
