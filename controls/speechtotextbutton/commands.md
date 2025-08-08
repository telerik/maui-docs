---
title: Commands
page_title: .NET MAUI SpeechToTextButton Documentation - Commands
description: Use the exposed commands of the Telerik UI for .NET MAUI SpeechToTextButton
position: 3
tags: .net maui, telerik speech to text button for .net maui, ui for .net maui, microsoft .net maui
slug: speechtotextbutton-commands
---

# .NET MAUI SpeechToTextButton Commands

The .NET MAUI SpeechToTextButton provides commands that execute when specific actions occur, such as when speech is recognized or when an error occurs. This allows you to handle these events in a more MVVM-friendly way.

The .NET MAUI SpeechToTextButton exposes the following commands:

* `SpeechRecognizedCommand` (`ICommand`)&mdash;Specifies a command to execute when the speech recognition is successful and the recognized text is available. The command context is `SpeechToTextButtonSpeechRecognizedCommandContext`, which contains the recognized text&mdash;`FullText` and confidence score&mdash;`FullTextConfidenceScore`.
* `ErrorOccurredCommand` (`ICommand`)&mdash;Specifies a command to execute when an error occurs during the speech recognition process. The command context is `SpeechToTextButtonErrorOccurredCommandContext`, which contains the error message&mdash;`Message` and the exception&mdash;`Exception`.

## Example

Here is an example using the `SpeechRecognizedCommand` and `ErrorOccurredCommand`:

**1.** Define the `SpeechToTextButton` in XAML:

<snippet id='speechtotext-commands' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Define the `ViewModel` with `SpeechRecognizedCommand` and `ErrorOccurredCommand` definitions:

<snippet id='speechtotext-commands-viewmodel' />

> For a runnable example with the SpeechToTextButton Commands scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **SpeechToTextButton > Features** category.

## See Also

- [Set Visual States]({%slug speechtotextbutton-visual-states%})
- [Events]({%slug speechtotextbutton-events%})
- [Custom Recognizer]({%slug speechtotextbutton-custom-recognizer%})
- [Style the SpeechToTextButton]({%slug speechtotextbutton-styling%})