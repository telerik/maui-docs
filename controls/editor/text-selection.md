---
title: Text Selection
page_title: .NET MAUI Editor Documentation - Text Selection
description: Learn how to specify the starting position of the selected text input and the number of characters in the current selection of the Telerik Editor for .NET MAUI control.
position: 3
slug: editor-text-selection
---

# .NET MAUI Editor Text Selection

The Editor supports a number of settings for managing the selection of its input text.

The text selection properties that are applicable for the Editor control are:

@[template](/_contentTemplates/controls/inputview.md#inputview-text-selection)

The following snippet shows how to use the `SelectionOnFocus` property to preselect the Editor text as soon as the control receives focus:

```XAML
<telerik:RadEditor x:Name="editor"
                   Text="some text here"
                   SelectionOnFocus="SelectAll" />
```

## See Also


- [Text Appearance]({%slug editor-text-appearance%})
- [Events]({%slug editor-events%})
- [Styling]({%slug editor-styling%})
- [Validation]({%slug editor-validation%})
- [Visual States]({%slug editor-visual-states%})