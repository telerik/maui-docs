---
title: Multiline TextInput
page_title: .NET MAUI TextInput Documentation - Multiline TextInput
description: Learn more about the Multiline TextInput control used inside the Telerik UI for .NET MAUI Editor controls.
position: 25
slug: editor-multiline-textinput
---

# Multiline TextInput

The Telerik UI for .NET MAUI Multiline TextInput is a control that allows users to enter and edit multiple lines of text. 

The Telerik UI for .NET MAUI Editor is a templated control, with a `ControlTemplate`, and in that `ControlTemplate` there are borders, a close button, and a Multiline TextInput.

The Multiline TextInput exposes the following properties:

* `SelectionOnFocus` (`enum` of type `Telerik.Maui.SelectionOnFocus`)&mdash;Specifies the text selection behavior when the Editor control receives focus. The available options are:
    * (Default) `Unchanged`&mdash;The selection will not be modified.
    * `CursorAtStart`&mdash;The cursor will be moved at the start of the text.
    * `CursorAtEnd`&mdash;The cursor will be moved at the end of the text.
    * `SelectAll`&mdash;The whole text will be selected.

* `Padding` (`Thickness`)&mdash;Defines the padding.
* `MaxLines` (`string`)&mdash;Defines the maximum number of lines to display before the control stops growing. The default value is `0`, so there is no limit.
* `Text` (`string`)&mdash;Defines the text of the Multiline TextInput.
* `MinimumHeightRequest` (`string`)&mdash;Defines the minimum height the element will request during layout.

The `RadMultilineTextInput` control inherits from the `Microsoft.Maui.Editor` control.
