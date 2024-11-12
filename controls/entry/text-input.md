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

Along with the properties the Telerik .NET MAUI TextInput control inherits from the Microsoft .NET MAUI Entry control, the Textinput exposes the following properties:

* `SelectionOnFocus` (`enum` of type `Telerik.Maui.SelectionOnFocus`)&mdash;Specifies the text selection behavior when the Entry control receives focus. The available options are:
    * (Default) `Unchanged`&mdash;The selection will not be modified.
    * `CursorAtStart`&mdash;The cursor will be moved at the start of the text.
    * `CursorAtEnd`&mdash;The cursor will be moved at the end of the text.
    * `SelectAll`&mdash;The whole text will be selected.

* `Padding` (`Thickness`)&mdash;Defines the padding.

## See Also

- [Entry Overview]({%slug entry-overview%})
- [Entry Styling]({%slug entry-styling%})
