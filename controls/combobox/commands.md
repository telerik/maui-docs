---
title: Commands
page_title: .NET MAUI ComboBox Documentation - Commands
description: Check our &quot;Commands&quot; documentation article for Telerik ComboBox for .NET MAUI control.
position: 8
slug: combobox-commands
---

# Commands

ComboBox has the following commands:

- `SelectAllCommand` (`ICommand`): Selects all items from the source.

> SelectAll command can be used only when `SelectionMode` is `Multiple`. An exception will be thrown, if the command is invoked in `Single` `SelectionMode`.

- `ClearSelectionCommand` (*ICommand*): Sets the selection to null. If Multiple SelectionMode is used, this command will clear all selected items.

## See Also

- [Configuration]({%slug combobox-configuration%})
- [Data Binding]({%slug combobox-databinding%})
- [Edit Mode & Search]({%slug combobox-editmode-and-search%}) 
- [Templates]({%slug combobox-templates%})
