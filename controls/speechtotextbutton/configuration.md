---
title: Configuration
page_title: .NET MAUI SpeechToTextButton Documentation - Configuration
description: Learn how to define language, get the text from the speech to text recognizer when using the Telerik SpeechToTextButton for .NET MAUI.
position: 3
tags: .net maui, telerik speech to text button for .net maui, ui for .net maui, microsoft .net maui
slug: speechtotextbutton-configuration
---

# .NET MAUI SpeechToTextButton Configuration

The purpose of this help article is to show you the main configuration options of the control.

## Getting Full Text from Speech Recognition

The SpeechToTextButton allows you to retrieve the full text recognized by the speech recognition service. 
This is done through the `FullText` property, which provides the complete transcription of the spoken input.

To get the full text, you can subscribe to the `SpeechRecognized` event, which is triggered when the speech recognition is successful.

## Continuous Recognition

The SpeechToTextButton supports continuous speech recognition, allowing it to listen for speech input without stopping after each recognition.

You can disable the continuous recognition by setting the `IsContinuousRecognition` property to `false`. The default value is `true`, meaning that the button will listen for speech input continuously, until it is explicitly stopped or the user taps the button again.

```XAML
<telerik:RadSpeechToTextButton x:Name="speechContinuousButton" 
							   IsContinuousRecognition="False"
							   SpeechRecognized="OnSpeechRecognized" />
```

## Language

The SpeechToTextButton allows you to set the language for speech recognition. This is important for accurate transcription of spoken words into text. 

You can set the language using the `LanguageTag` property, which accepts a string representing the language code (e.g., "en-US" for English, "fr-FR" for French).

<snippet id='speechtotext-language-tag' />

> For a runnable example with the SpeechToTextButton Getting Started scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **SpeechToTextButton > Configuration** category.

## See Also

- [Set Visual States]({%slug speechtotextbutton-visual-states%})
- [Execute Commands]({%slug speechtotextbutton-commands%})
- [Style the SpeechToTextButton]({%slug speechtotextbutton-styling%})