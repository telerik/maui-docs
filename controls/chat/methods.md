---
title: Methods
page_title: .NET MAUI Chat Documentation - Methods
description: Learn about the public methods of the Telerik UI for .NET MAUI Chat control.
position: 10
slug: chat-methods
---

# .NET MAUI Chat Methods

The Telerik UI for .NET MAUI Chat exposes methods that let you interact with the input area from code.

## Focus the Input

Use the `FocusEntry()` method to move keyboard focus to the Chat input entry.

The method returns `true` when the focus change succeeds and `false` when the call does not focus the input element.

```C#
bool isFocused = this.chat.FocusEntry();
```

## Stop Speech-to-Text Recognition

Use the `StopSpeechToTextRecognition()` method to stop the active speech-to-text recognition session.

If the speech recognizer is currently listening, the method stops the recognition process. If the recognizer is not active, the call has no effect.

```C#
await this.chat.StopSpeechToTextRecognition();
```

## See Also

- [Scrolling]({%slug chat-scrolling%})
- [Buttons Styling]({%slug chat-buttons-styling%})