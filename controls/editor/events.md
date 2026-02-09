---
title: Events
page_title: .NET MAUI Editor Documentation - Events
description: Learn how to use the exposed events of the Telerik UI for .NET MAUI Editor control.
position: 5
tags: editor, input text, event, .net maui, text changed, enter key, completed event, input control
slug: editor-events
---

# .NET MAUI Editor Events

The Telerik UI for .NET MAUI Editor control exposes a number of events and commands for notifying after user interactions.

The Editor supports the following events:

@[template](/_contentTemplates/controls/inputview.md#inputview-events)

The `Completed` event is raised when the Editor control losses focus.

The following example demonstrates the Editor definition in XAML with the `TextChanged` and `Completed` event handlers.

**1.** Define the Editor.

<snippet id='editor-events-xaml' />

**2.** Add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Set the `TextChanging` event.

<snippet id='editor-events-text-changing' />

**3.** Set the `Completed` event.

<snippet id='editor-events-completed' />

![Editor Events](images/editor-events.gif)

## See Also

- [Text Appearance]({%slug editor-text-appearance%})
- [Text Selection]({%slug editor-text-selection%})
- [Styling]({%slug editor-styling%})
- [Validation]({%slug editor-validation%})
- [Visual States]({%slug editor-visual-states%})