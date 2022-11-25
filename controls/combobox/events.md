---
title: Events
page_title: .NET MAUI ComboBox Documentation - Events
description: Check our &quot;Evenys&quot; documentation article for Telerik ComboBox for .NET MAUI control.
position: 7
slug: combobox-events
---

# .NET MAUI ComboBox Events

ComboBox for .NET MAUI exposes the following events:

- `SelectionChanged` event is raised when item is selected. The SelectionChanged event handler receives two parameters:
	- The `sender` which is the RadComboBox control.
	- ComboBoxSelectionChangedEventArgs provides the following properties:
		- `AddedItems`: the items added to the SelectedItemsCollection
		- `RemovedItems`: the items removed from the SelectedItemsCollection

- `Completed`: Invoked when the completed button of the keyboard gets pressed. In UWP it is invoked when entered gets pressed. 

## See Also

- [Configuration]({%slug combobox-configuration%})
- [Header and Footer]({%slug combobox-header-footer%})
- [Edit Mode & Search]({%slug combobox-editmode-and-search%}) 
- [Single and Multiple Selection]({%slug combobox-selection%})
- [Styling]({%slug combobox-styling%})
- [Commands]({%slug combobox-commands%})
