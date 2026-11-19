---
title: Enabling Single-Tap Editing and Restoring Selection in the DataGrid
page_title: DataGrid Tap Selection and Rebinding | Telerik UI for .NET MAUI
description: Test single-tap editing and row or cell selection in the .NET MAUI DataGrid, and reapply the last selection after DataBindingComplete.
type: how-to
slug: datagrid-kb-selection-after-taps
tags: datagrid, maui, row selection, cell selection, single-tap editing, celltap, celldoubletap, databindingcomplete, selectionchanged, diagnostics
res_type: kb
---

## Environment

| Property | Value |
|----------|-------|
| Product | Telerik UI for .NET MAUI |
| Version | Not specified |
| Platform | Not specified |

## Description

This article shows how to start cell editing with a single tap and explicitly select the tapped row or cell in the DataGrid. A custom `CellTap` command invokes the default `CellDoubleTap` behavior, then calls `SelectItem` or `SelectCell` according to `SelectionUnit`.

The sample remembers the last tapped cell and reapplies its row or cell selection when `DataBindingComplete` occurs. This restoration assumes that the same data item and column remain available. The example uses `SelectionMode="Single"` and does not restore a collection of multiple selections.

Debug output records `CellTap`, `SelectionChanged`, and `DataBindingComplete` to help you trace the interaction. The approach requires the grid to invoke `CellTap`; it cannot recover an unrecognized tap and is not a confirmed fix for missed taps.

## Solution

Create a page with a DataGrid and a small data source. The sample uses single selection and row selection. Set `SelectionUnit` to `Cell` to test cell selection.

```xml
<ContentPage xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
             x:Class="TapSelectionDiagnostic.TapSelectionPage">
    <telerik:RadDataGrid x:Name="grid"
                         ItemsSource="{Binding People}"
                         SelectionMode="Single"
                         SelectionUnit="Row"
                         UserEditMode="Cell" />
</ContentPage>
```

Add a command that routes each `CellTap` to `CellDoubleTap` and then selects the tapped row or cell:

```csharp
using System;
using System.Diagnostics;
using Telerik.Maui.Controls.DataGrid;

namespace TapSelectionDiagnostic;

public sealed class CellTapSelectCommand : DataGridCommand
{
    private DataGridCellInfo lastTappedCell;

    public CellTapSelectCommand()
    {
        this.Id = DataGridCommandId.CellTap;
    }

    public override bool CanExecute(object parameter)
    {
        return parameter is DataGridCellInfo;
    }

    public override void Execute(object parameter)
    {
        if (parameter is not DataGridCellInfo cell)
        {
            throw new ArgumentException(
                "CellTap requires a DataGridCellInfo parameter.",
                nameof(parameter));
        }

        this.lastTappedCell = cell;
        Debug.WriteLine($"CellTap received for item: {cell.Item}");

        this.Owner.CommandService.ExecuteDefaultCommand(
            DataGridCommandId.CellDoubleTap,
            cell);

        this.ApplySelection(cell);
    }

    public void ReapplySelection()
    {
        if (this.lastTappedCell is not null)
        {
            this.ApplySelection(this.lastTappedCell);
        }
    }

    private void ApplySelection(DataGridCellInfo cell)
    {
        switch (this.Owner.SelectionUnit)
        {
            case DataGridSelectionUnit.Row:
                this.Owner.SelectItem(cell.Item);
                break;
            case DataGridSelectionUnit.Cell:
                this.Owner.SelectCell(cell);
                break;
            default:
                throw new ArgumentOutOfRangeException(
                    nameof(this.Owner.SelectionUnit));
        }
    }
}
```

Register the command and log selection and data-binding events in the page:

```csharp
using System.Diagnostics;
using Microsoft.Maui.Controls;
using Telerik.Maui.Controls.DataGrid;

namespace TapSelectionDiagnostic;

public partial class TapSelectionPage : ContentPage
{
    private readonly CellTapSelectCommand tapCommand = new();

    public TapSelectionPage()
    {
        this.InitializeComponent();

        this.grid.Commands.Add(this.tapCommand);
        this.grid.DataBindingComplete += this.OnDataBindingComplete;
        this.grid.SelectionChanged += this.OnSelectionChanged;
        this.BindingContext = new TapSelectionViewModel();
    }

    private void OnDataBindingComplete(
        object sender,
        DataBindingCompleteEventArgs e)
    {
        Debug.WriteLine($"DataBindingComplete: {e.ChangeFlags}");
        this.tapCommand.ReapplySelection();
    }

    private void OnSelectionChanged(
        object sender,
        DataGridSelectionChangedEventArgs e)
    {
        Debug.WriteLine(
            $"SelectionChanged. Selected items: {this.grid.SelectedItems.Count}");
    }
}
```

Add a data source with a few records:

```csharp
using System.Collections.ObjectModel;

namespace TapSelectionDiagnostic;

public sealed class TapSelectionViewModel
{
    public ObservableCollection<Person> People { get; } = new()
    {
        new Person { Name = "Avery" },
        new Person { Name = "Jordan" },
        new Person { Name = "Morgan" },
        new Person { Name = "Taylor" }
    };
}

public sealed class Person
{
    public string Name { get; set; }
}
```

Run the page and tap different rows. Then set `SelectionUnit` to `Cell` and repeat. Check the debug output to confirm whether `CellTap` arrives and whether `SelectionChanged` follows.

## Notes

The default `CellDoubleTap` command begins editing. It does not select the row or cell. This sample calls `SelectItem` or `SelectCell` after invoking that command. `UserEditMode="Cell"` enables editing, so a single tap in this sample can enter edit mode.

`DataBindingComplete` occurs after the grid binds its `ItemsSource` or applies a data operation. It does not occur after every tap. The sample retains the last tapped item and cell, so reapplication assumes that the same item and column remain in the grid. If you replace the data objects or columns, resolve the current item and column before restoring selection.

`SelectionUnit` controls row or cell selection. `SelectionMode` controls whether the grid allows single, multiple, or no selection.

## See Also

* [DataGrid selection options]({%slug datagrid-selection-overview%})
* [Handling DataGrid cell taps]({%slug datagrid-commands-cell-tap%})
* [Handling DataGrid data-binding events]({%slug datagrid-events%})
