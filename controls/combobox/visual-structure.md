---
title: Visual Structure
page_title: .NET MAUI ComboBox Documentation - ComboBox Visual Structure
description: Learn more about the visual elements used in the Telerik UI for .NET MAUI ComboBox control.
position: 0
slug: combobox-visual-structure
---

# .NET MAUI ComboBox Visual Structure

The visual structure of the [.NET MAUI ComboBox]({%slug combobox-overview%}) represents the anatomy of the UI control. Being familiar with the visual elements of the ComboBox allows you to quickly find the information required to configure them.

The images in this article show the anatomy of the ComboBox and its building blocks.

## ComboBox Visual Structure

![Telerik UI for .NET MAUI ComboBox Placeholder Visual Structure](images/combobox-visual-structure.png "Visual elements of ComboBox control")

- `Placeholder`&mdash;The text that guides the end-user on what can be entered/searched in the input.
- `DropDown Button`&mdash;A button used for opening and closing the DropDown part of the control–the arrow icon of the button indicates whether it's currently opened or closed.

## Single Selection Structure

![Telerik UI for .NET MAUI ComboBox Single Selection Visual Structure](images/combobox-single-selection-visual-structure.png "Visual elements of ComboBox control")

- `Text`&mdash;The text entered in the control's input filed.
- `Clear Button`&mdash;Clears the selection in the control (for both multiple and single selection scenarios).
- `DropDown Button`&mdash;A button used for opening and closing the DropDown part of the control–the arrow icon of the button indicates whether it's currently opened or closed.
- `Selected Item`&mdash;The currently selected item.

## Tokens Structure

![Telerik UI for .NET MAUI ComboBox Tokens Visual Structure](images/combobox-multiple-selection-visual-structure.png "Visual elements of ComboBox control")

- `Tokens`&mdash;When multiple items are selected from the dropdown list, these items appear as tokens. They can be deselected using their close button.
- `ShowMore Template`&mdash;This template represents a UI that is displayed when the control is not focused and the space is insufficient to show all tokens in a multiple selection scenario.

## Multiple Selection Structure

![Telerik UI for .NET MAUI ComboBox DropDown Multiple Selection Visual Structure](images/dropdown-multiple-selection.png "Visual elements of ComboBox control")

- `Tokens`&mdash;When multiple items are selected from the dropdown list, these items appear as tokens. They can be deselected using their close button.
- `SelectedItems`&mdash;The selected items when multiple selection is used.
- `ShowMore Template`&mdash;This template represents a UI that is displayed when the control is not focused and the space is insufficient to show all tokens in a multiple selection scenario.

## Edit Mode Structure

![Telerik UI for .NET MAUI ComboBox Edit Mode Visual Structure](images/combo-editmode.png "Visual elements of ComboBox control")

- `Clear Button`&mdash;Clears the selection in the control (for both multiple and single selection scenarios).
- `DropDown Button`&mdash;A button used for opening and closing the DropDown part of the control–the arrow icon of the button indicates whether it's currently opened or closed.
- [`RadTextInput`]({%slug entry-textinput%})&mdash;The control used for the text input.
- `Text`&mdash;The text entered in the control's input filed.
- `Highlighted Items`&mdash;The items that match the text entered in the input area.
