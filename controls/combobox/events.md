---
title: Events
page_title: .NET MAUI ComboBox Documentation - Events
description: Check our &quot;Evenys&quot; documentation article for Telerik ComboBox for .NET MAUI control.
position: 8
slug: combobox-events
---

# .NET MAUI ComboBox Events

The [.NET MAUI ComboBox]({%slug combobox-overview%}) exposes the following events:

- `SelectionChanged` event is raised when item is selected. The SelectionChanged event handler receives two parameters:
	- The `sender` which is the RadComboBox control.
	- `ComboBoxSelectionChangedEventArgs` provides the following properties:
		- `AddedItems`: the items added to the `SelectedItems`
		- `RemovedItems`: the items removed from the `SelectedItems`

- `Completed`: Invoked when the inner editable `RadTextInput` completes input (for example, when the keyboard completion/Enter action is pressed in edit mode). This event is tied to text input completion, not to general Enter handling in all ComboBox modes. 

## See Also

- [Configuration]({%slug combobox-configuration%})
- [Header and Footer]({%slug combobox-header-footer%})
- [Edit Mode & Search]({%slug combobox-editmode-and-search%}) 
- [Single and Multiple Selection]({%slug combobox-selection%})
- [Styling]({%slug combobox-styling%})
- [Commands]({%slug combobox-commands%})
