---
title: TextInput
page_title: .NET MAUI TextInput Documentation - TextInput
description: Learn more about the TextInput control used inside the Telerik UI for .NET MAUI Entry controls.
position: 25
slug: entry-textinput
---

# TextInput

The Telerik UI for .NET MAUI TextInput is a control that inherits from the Microsoft .NET MAUI Entry control.

The Telerik UI for .NET MAUI Entry control uses the TextInput control in its control template for the text input. The Telerik UI for .NET MAUI Entry is a templated control, with a `ControlTemplate`, and in that `ControlTemplate` there are borders, a close button, and a TextInput.

The TextInput control exposes the following properties:

* `SelectionOnFocus` (`enum` of type `Telerik.Maui.SelectionOnFocus`)&mdash;Specifies the text selection behavior when the Entry control receives focus. The available options are:
    * (Default) `Unchanged`&mdash;The selection will not be modified.
    * `CursorAtStart`&mdash;the cursor will be moved at the start of the text.
    * `CursorAtEnd`&mdash;the cursor will be moved at the end of the text.
    * `SelectAll`&mdash;the whole text will be selected.

* `Text` (`string`)&mdash;Defines the text.
* `Padding` (`Thickness`)&mdash;Defines the padding.

## Events

The TextInput exposes the `TextChanging` event that is raised when the text in the Entry starts to change, but before the `Text` property is updated. The `TextChanging` event handler receives a `TextChangingEventArgs` argument containing data related to this event. The `TextChangedEventArgs` provides the following properties:
* `NewText` (`string`)&mdash;Gets the new text that is about to be entered into the entry.
* `OldText` (`string`)&mdash;Gets the old text that is entered into the entry.
* `Cancel` (`bool`)&mdash;Gets or sets a value that indicates whether to cancel the text changes.

## See Also

- [Entry Overview]({%slug entry-overview%})
- [Entry Styling]({%slug entry-styling%})
