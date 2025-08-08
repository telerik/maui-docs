---
title: WinUI Support
page_title: .NET MAUI SpeechToTextButton Documentation - WinUI Support
description: Review what are the options and limitations using the .NET MAUI SpeechToTextButton on WinUI.
position: 1
slug: speechtotextbutton-winui-support
---

# .NET MAUI SpeechToTextButton WinUI Support Specifics

The Telerik UI for .NET MAUI SpeechToTextButton control is designed to work seamlessly across all supported platforms, including WinUI.

The Speech Recognizer uses platform-specific speech recognition services. On WinUI, it relies on the [`Windows.Media.SpeechRecognition`](https://learn.microsoft.com/en-us/uwp/api/windows.media.speechrecognition?view=winrt-26100). However, there are specific considerations when using the control on WinUI due to platform limitations.

## Limitations in Windows.Media.SpeechRecognition

* The app crashes when trying to close the application via the "X" button and the app is **Packaged**. There is an open bug report: [Application crashes after using SpeechRecognizer in a Packaged App](https://github.com/microsoft/microsoft-ui-xaml/issues/10697)

* Based on this issue, the SpeechToTextButton control is not fully supported on WinUI. When you click the control, an `InvalidOperationException` is thrown.

## Solutions

To use the SpeechToTextButton on WinUI, you can use one of the following approaches:

* Set the `SpeechRecognizerCreator` property of the `RadSpeechToTextButton` to `RadSpeechRecognizer` for **Unpackaged** apps:

```csharp
this.speechToTextButton.SpeechRecognizerCreator = () => new RadSpeechRecognizer();
```

* Create a [custom recognizer]({%slug speechtotextbutton-custom-recognizer%}) for **Packaged** and **Unpackaged** apps.

* Use an **Unpackaged** app deployment model.

## Language Support

When setting the `LanguageTag` to a specific value, ensure that the language is supported by the `Windows.Media.SpeechRecognition.SpeechRecognizer` on WinUI. 

For more details, review the [Microsoft documentation](https://learn.microsoft.com/en-us/windows/apps/design/input/speech-recognition#predefined-grammars).

## See Also

- [Visual States in the SpeechToTextButton]({%slug speechtotextbutton-visual-states%})
- [Configure the SpeechToTextButton]({%slug speechtotextbutton-configuration%})
- [Events]({%slug speechtotextbutton-events%})
- [Execute Commands]({%slug speechtotextbutton-commands%})