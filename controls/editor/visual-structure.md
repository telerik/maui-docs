---
title: Visual Structure
page_title: .NET MAUI Editor Documentation - Editor Visual Structure
description: Learn more about the visual elements used in the Telerik UI for .NET MAUI Editor control.
position: 0
slug: editor-visual-structure
---

# .NET MAUI Editor Visual Structure

The visual structure of the [.NET MAUI Editor]({%slug editor-overview%}) represents the anatomy of the UI control. Being familiar with the visual elements of the Editor allows you to quickly find the information required to configure them.

The images in this article show the anatomy of the Editor and its building blocks.

## Editor Visual Structure

![Telerik UI for .NET MAUI Editor Visual Structure](images/editor-focused-text.png "Visual elements of Editor control")

- `Placeholder`&mdash;The text that guides the end-user on what can be entered/searched in the input.
- [`RadMultilineTextInput`]({%slug editor-multiline-textinput%})&mdash;The control used for the multiline text input.

## Input Structure

![Telerik UI for .NET MAUI Editor Input Visual Structure](images/editor-valid-text.png "Visual elements of Editor control")

- `Text`&mdash;The text entered in the control's input field.
- [`RadMultilineTextInput`]({%slug editor-multiline-textinput%})&mdash;The control used for the multiline text input.
- `Clear Button`&mdash;Clears the selection in the control for both multiple and single selection scenarios.

## Validation Structure

![Telerik UI for .NET MAUI Editor Validation Visual Structure](images/winui-entry.png "Visual elements of Editor control")

- `Text`&mdash;The text entered in the control's input field.
- `Clear Button`&mdash;Clears the selection in the control for both multiple and single selection scenarios.
- `Style when IsValueValid is False`&mdash;Specifies the style applied when the value entered in the input field is invalid.
- `Invalid Image`&mdash;An image is displayed when the input value is invalid.


## See Also

- [Text Appearance]({%slug editor-text-appearance%})
- [Text Selection]({%slug editor-text-selection%})
- [Events]({%slug editor-events%})
- [Styling]({%slug editor-styling%})
- [Validation]({%slug editor-validation%})
- [Visual States]({%slug editor-visual-states%})