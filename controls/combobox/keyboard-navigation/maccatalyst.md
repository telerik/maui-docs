---
title: MacCatalyst
page_title: .NET MAUI ComboBox Documentation - Keyboard Support on MacCatalyst
description: Learn more about the available keyboard combinations as part of the supported Telerik UI for .NET MAUI ComboBox accessibility standards.
position: 1
slug: combobox-keyboard-support-mac
---

# .NET MAUI ComboBox Keyboard Support on MacCatalyst

The Telerik UI for .NET MAUI ComboBox provides keyboard navigation support on `MacCatalyst`.

The following table lists the actions and keyboard combinations that are available in the ComboBox:

| Hotkey Combinations  | Action 		   |
|----------------------|-------------------|
| `F4` | Shows the dropdown if it is closed. If the dropdown is opened pressing the F4 key will submit the selection and close the dropdown. |
| `Up Arrow` / `Down Arrow` | If the dropdown is opened pressing Up/Down Arrows will change the highlighted item in the dropdown list. If it is closed pressing Up/Down Arrows will change the SelectedItem.|
| `Left Arrow` / `Right Arrow` | If the dropdown is opened pressing Left/Right Arrows will change the highlighted item in the dropdown list. If it is closed pressing Left/Right Arrows will change the SelectedItem. They work only when `IsEditable` is `False`. |
| `Enter` |Takes effect only when the dropdown of the ComboBox is opened. Commits the selection and closes the dropdown. |
| `Esc`	| Works only when `IsEditable` is `False` and the dropdown is opened. It cancels the selection and closes the dropdown of the ComboBox. |
| `Home` / `End` | Works only when `IsEditable` is `False`. When the dropdown is opened pressing the Home/End keys will change the highlighted item to the first/last item. If the dropdown is closed pressing the Home/End keys will change the selected item to the first/last item.|
| `PageUp` / `PageDown` | Pressing any of these keys will open the dropdown when it is closed. If the dropdown is opened pressing PageUp/PageDown will change the highlighted item. |

>When `IsEditable` property of the ComboBox is `True`, `Command` key should be pressed to enable the previously described hotkeys.

## See Also

- [Edit Mode & Search]({%slug combobox-editmode-and-search%}) 
- [Single and Multiple Selection]({%slug combobox-selection%})