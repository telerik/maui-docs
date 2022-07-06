---
title: Keyboard
page_title: .NET MAUI DataGrid Documentation | Keyboard
description: Check our &quot;Keyboard&quot; documentation article for Telerik DataGrid for .NET MAUI control.
position: 9
slug: datagrid-keyboard
---

# Keyboard

RadDataGrid exposes several useful properties and events, which can help you control the keyboard interaction and get notified when keyboard events occur.

In the following table you can find some of the actions and the respective hotkeys that invoke them:

| Hotkey 		    | Action 			|
|-------------------|-------------------|
| `Arrow Keys`      | Тhe current cell will be changed. The selection will be changed as well when in single mode.|
| `F2`              |Enter in edit mode of the current cell.|
| `Enter `	        |Select next/previous row. When in edit mode the changes will be committed and the next row will be selected.|
| `Esc `		    |Cancel the editing of the cell if such is present.|
| `PageUp `		    |When `Ctrl` is pressed it will change current cell to be first cell. Without `Ctrl` the control will scroll down based on the number of items in the viewport.|
| `PageDown `	    |When `Ctrl` is pressed it will change the current cell to be last cell. Without `Ctrl` the control will scroll up based on the number of items in the viewport.|
| `Home `	        |Focus first cell of selected cell. When `Ctrl` is pressed - focus the first cell of the grid.|
| `End  `	        |Focus last cell of selected cell. When `Ctrl` is pressed - focus the last cell of the grid.|
| `Tab  `	        |Focus next cell or previous cell when shift is pressed. We will try to focus the next/previous editor when in edit mode. |

## Properties

* `CurrentCell`&mdash;property of type DataGridCellInfo.
* `CurrentCellChanged`&mdash;invoked when the current cell changes.
* `CurrentCellStyle`&mdash;style for the current cell decoration.

## See Also

- [Getting Started]({%slug datagrid-getting-started%})
- [Selection]({%slug datagrid-selection-overview%})
- [Sorting]({%slug datagrid-sorting-overview%})
- [Filtering]({%slug datagrid-filtering-overview%})
- [Grouping]({%slug datagrid-grouping-overview%})
- [Editing]({%slug datagrid-editing%})
