---
title: Implementing Additional Logic for Shift+Enter Keys in DataGrid on Windows
description: Learn how to implement custom logic for Shift+Enter keyboard keys in the DataGrid component for UI for .NET MAUI on Windows.
type: how-to
page_title: How to Handle Shift+Enter Keys in DataGrid for .NET MAUI
meta_title: Shift+Enter Key Handling in DataGrid for .NET MAUI
slug: handle-shift-enter-keys-datagrid-dotnet-maui
tags: datagrid, keyboard, shift, enter, windows, .net maui, radkeyboardkey
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 12.1.0 | Telerik UI for .NET MAUI DataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to implement additional logic for handling `Shift`+`Enter` keyboard keys in the [DataGrid](https://www.telerik.com/maui-ui/documentation/controls/datagrid/overview) component on Windows. The `RadKeyboardKey` enumeration doesn't include the `Shift` key, and I need a way to determine if the `Shift` key is pressed.

This knowledge base article also answers the following questions:
- How to detect `Shift` key press in DataGrid for UI for .NET MAUI?
- How to override default key handling in DataGrid on Windows?
- How to execute custom logic for `Shift`+`Enter` keys in .NET MAUI DataGrid?

## Solution

To achieve this, extend the key handling logic in the `Execute` method of the DataGrid `KeyDownCommand`. Use the `Microsoft.UI.Input.InputKeyboardSource.GetKeyStateForCurrentThread` method to detect the `Shift` key press on Windows. Follow these steps:

1. Use the DataGrid `KeyDownCommand`. Define a class by inheriting from `DataGridCommand`.
2. Override the `Execute` method to implement logic for handling the `Shift` key.
3. Use the `IsShiftKeyDown` method to detect if the `Shift` key is pressed.

```csharp
using System.Collections.ObjectModel;
using System.Reflection;
using Telerik.Maui.Controls;
using Telerik.Maui.Controls.DataGrid;
#if WINDOWS
using Windows.UI.Core;
#endif

public class ShiftEnterDataGridKeydownCommand : DataGridCommand
{
	public ShiftEnterDataGridKeydownCommand()
	{
		Id = DataGridCommandId.KeyDown;
	}

	public override bool CanExecute(object parameter)
	{
		return true;
	}
	public override void Execute(object parameter)
	{
		if (parameter is KeyboardInfo keyboardInfo)
		{
			if (keyboardInfo.key == Telerik.Maui.RadKeyboardKey.Down)
			{
				var newKey = new KeyboardInfo(Telerik.Maui.RadKeyboardKey.Enter, () => { });
				this.Owner.CommandService.ExecuteDefaultCommand(Id, newKey);

			}
			else if (keyboardInfo.key == Telerik.Maui.RadKeyboardKey.Enter)
			{
				if (IsShiftKeyDown())
				{
					// add your logic here
					return;
				}
			}

			else
			{
				this.Owner.CommandService.ExecuteDefaultCommand(Id, parameter);
			}
		}
	}

	internal static bool IsShiftKeyDown(VisualElement visualElement = null)
	{
#if WINDOWS
		CoreVirtualKeyStates controlStates = Microsoft.UI.Input.InputKeyboardSource.GetKeyStateForCurrentThread(global::Windows.System.VirtualKey.Shift);
		bool isShiftKeyDown = controlStates.HasFlag(CoreVirtualKeyStates.Down);

		return isShiftKeyDown;

#else
		return false;
#endif
	}
}
```

## See Also

- [DataGrid Overview](https://www.telerik.com/maui-ui/documentation/controls/datagrid/overview)
- [DataGrid Keyboard Support](https://www.telerik.com/maui-ui/documentation/controls/datagrid/keyboard-navigation/windows)
- [DataGrid Commands](https://www.telerik.com/maui-ui/documentation/controls/datagrid/commands/overview)
