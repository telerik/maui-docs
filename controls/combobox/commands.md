---
title: Commands
page_title: .NET MAUI ComboBox Documentation - Commands
description: Learn more about the commands that the Telerik UI for .NET MAUI ComboBox control exposes.
position: 8
slug: combobox-commands
---

# .NET MAUI ComboBox Commands

ComboBox has the following commands:

- `SelectAllCommand` (`ICommand`)&mdash;Selects all items from the source.

> The `SelectAll` command can be used only when `SelectionMode` is `Multiple`. An exception will be thrown if the command is invoked in `Single` `SelectionMode`.

- `ClearSelectionCommand` (`ICommand`)&mdash;Sets the selection to null. If Multiple `SelectionMode` is used, this command will clear all selected items.

Here is an example with `ClearSelectionCommand`:

<snippet id='combobox-commands'/>

<snippet id='combobox-commands-csharp'/>

![ComboBox ClearSelectionCommand](images/combobox-commands.gif)

## See Also

- [Configuration]({%slug combobox-configuration%})
- [Data Binding]({%slug combobox-databinding%})
- [Edit Mode & Search]({%slug combobox-editmode-and-search%}) 
- [Templates]({%slug combobox-templates%})
