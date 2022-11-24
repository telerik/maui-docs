---
title: Keyboard Support
page_title: .NET MAUI DataGrid Documentation - Keyboard Support
description: Check the Telerik DataGrid for .NET MAUI Keyboard navigation article.
position: 9
slug: datagrid-keyboard-support
---

# .NET MAUI DataGrid Keyboard Support

RadDataGrid provides keyboard navigation support which is curently available on WinUI. You can easily change the DataGrid `CurrentCell` when using some of the keyboard keys. For more details about CurentCell review the [Current Cell]({%slug datagrid-current-cell%}) article	

In the following table you can find some of the actions and the respective hotkeys that invoke them:

| Hotkey 		    | Action 			|
|-------------------|-------------------|
| `Left Arrow Key`  | Focus next cell on the left. The selection is changed as well when in single mode. |
| `Right Arrow Key` | Focus next cell on the right. The selection is changed as well when in single mode. |
| `Up Arrow Key`    | Focus next cell above. The selection is changed as well when in single mode. |
| `Down Arrow Key`  | Focus next cell below. The selection is changed as well when in single mode. |
| `F2`              | Put current cell in edit mode. |
| `Enter`	        | Select next/previous row. When in edit mode the changes are committed and the next row is selected. |
| `Esc`				| Cancel the editing of the current cell. |
| `PageUp`		    | Focus first cell of view port. |
| `PageDown`	    | Focus last cell of view port. |
| `Home`	        | Focus first cell of selected row. |
| `End`				| Focus last cell of selected row. |
| `Ctrl + Home`		| Focus first cell of grid. |
| `Ctrl + End`		| Focus last cell of grid. |
| `Tab `	        | Focus next cell. When in edit mode - next cell editor is focused. |
| `Shift + Tab`		| Focus previous cell. When in edit mode - previous editor is focused. |

## See Also

- [Getting Started]({%slug datagrid-getting-started%})
- [Selection]({%slug datagrid-selection-overview%})
- [Sorting]({%slug datagrid-sorting-overview%})
- [Filtering]({%slug datagrid-filtering-overview%})
- [Grouping]({%slug datagrid-grouping-overview%})
- [Editing]({%slug datagrid-editing%})
