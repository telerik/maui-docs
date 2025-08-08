---
title: Custom Recognizer
page_title: .NET MAUI SpeechToTextButton Documentation - Custom Recognizer
description: Learn how to use a custom speech recognizer with the Telerik SpeechToTextButton for .NET MAUI.
position: 6
tags: .net maui, telerik speech to text button for .net maui, ui for .net maui, custom recognizer, microsoft .net maui
slug: speechtotextbutton-custom-recognizer
---

# .NET MAUI SpeechToTextButton Custom Recognizer

The .NET MAUI SpeechToTextButton allows you to use a custom speech recognizer by implementing the `IRadSpeechRecognizer` interface. This enables you to integrate third-party speech recognition services or customize the behavior of the speech recognition process.

## Implementation Steps

Follow these steps to implement a custom speech recognizer:

**1.** Define the `SpeechToTextButton` in XAML:

<snippet id='speechtotext-custom-recognizer' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Create a class `MyCustomSpeechRecognizer` that implements the `IRadSpeechRecognizer` interface:

<snippet id='speechtotext-mycustomrecognizer' />

**4.** Set the `SpeechRecognizerCreator` property of the `RadSpeechToTextButton` to an instance of your custom recognizer:

<snippet id='speechtotext-speech-recognizer-creator' />

**5.** Handle the `SpeechRecognized` event to process the recognition results:

<snippet id='speechtotext-events-speech-recognized' />

> For a runnable example with the SpeechToTextButton Commands scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **SpeechToTextButton > Features** category.

## See Also

- [Set Visual States]({%slug speechtotextbutton-visual-states%})
- [Events]({%slug speechtotextbutton-events%})
- [Style the SpeechToTextButton]({%slug speechtotextbutton-styling%})