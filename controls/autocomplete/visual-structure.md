---
title: Visual Structure
page_title: .NET MAUI AutoComplete Documentation - AutoComplete Visual Structure
description: Learn more about the visual elements used in the Telerik UI for .NET MAUI AutoComplete control.
position: 0
slug: autocomplete-visual-structure
---

# .NET MAUI AutoComplete Visual Structure

The visual structure of the [.NET MAUI AutoComplete]({%slug autocomplete-overview%}) represents the anatomy of the UI control. Being familiar with the visual elements of the AutoComplete allows you to quickly find the information required to configure them.

The images in this article show the anatomy of the AutoComplete and its building blocks.

![Telerik UI for .NET MAUI AutoComplete Visual Structure](images/autocomplete-placeholder.png "Visual elements of AutoComplete control")

- `Placeholder`&mdash;The text that guides the end-user on what can be entered/searched in the input.

## Tokens Structure

![Telerik UI for .NET MAUI AutoComplete Tokens Visual Structure](images/autocomplete-tokens-template.png "Visual elements of AutoComplete control")

- `Tokens`&mdash;When multiple items are selected from the dropdown list, these items appear as tokens. They can be deselected using their close button.
- `ShowMore Template`&mdash;This template represents a UI that is displayed when the control is not focused and the space is insufficient to show all tokens in a multiple selection scenario.

## Filtering Structure

![Telerik UI for .NET MAUI AutoComplete Filtering Visual Structure](images/autocomplete-focused-text.png "Visual elements of AutoComplete control")

- `Text`&mdash;The text entered in the control's input filed.
- [`RadTextInput`]({%slug entry-textinput%})&mdash;The control used for the text input.
- `Clear Button`&mdash;Clears the selection in the control (for both multiple and single selection scenarios).
- `Filtered Items`&mdash;The items that are displayed after filtering the `ItemsSource` of the AutoComplete control.
