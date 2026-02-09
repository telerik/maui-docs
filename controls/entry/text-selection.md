---
title: Text Selection
page_title: .NET MAUI Entry Documentation - Text Selection
description: Learn how to specify the starting position of the selected text input and the number of characters in the current selection of the Telerik Entry for .NET MAUI control.
position: 3
previous_url: /controls/entry/entry-text-selection
slug: entry-text-selection
---

# .NET MAUI Entry Text Selection

The Entry supports a number of settings for managing the selection of its input text.

The text selection properties provided by the Entry are:

@[template](/_contentTemplates/controls/inputview.md#inputview-text-selection)

The following snippet shows how to use the `SelectionOnFocus` property to preselect the Entry text as soon as the control receives focus:

```XAML
<telerik:RadEntry x:Name="entry"
                  Text="some text here"
                  SelectionOnFocus="SelectAll" />
```

## See Also

- [Events]({% slug entry-events%})
- [Styling]({% slug entry-styling%})