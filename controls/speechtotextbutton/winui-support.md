---
title: WinUI Support
page_title: .NET MAUI SpeechToTextButton Documentation - WinUI Support
description: Review what are the options and limitations using the .NET MAUI SpeechToTextButton on WinUI.
position: 3
slug: speechtotextbutton-winui-support
---

# .NET MAUI SpeechToTextButton WinUI Support Specifics

The Telerik UI for .NET MAUI SpeechToTextButton control is designed to work seamlessly across all supported platforms, including WinUI.

The Speech Recognizer uses platform-specific speech recognition services. By default, the `RadSpeechToTextButton` control uses the `RadSpeechRecognizer` as a speech recognizer creator. 

On WinUI, the `RadSpeechRecognizer` is not set to the `RadSpeechToTextButton`. When you click the control, an `InvalidOperationException` is thrown. The reason behind this is a limitation in the WinUI platform speech recognition service&mdash;[`Windows.Media.SpeechRecognition`](https://learn.microsoft.com/en-us/uwp/api/windows.media.speechrecognition?view=winrt-26100).

The `RadSpeechRecognizer` on WinUI utilizes the [`Windows.Media.SpeechRecognition`](https://learn.microsoft.com/en-us/uwp/api/windows.media.speechrecognition?view=winrt-26100). There are specific considerations when using the control on WinUI due to limitations in the `Windows.Media.SpeechRecognition` API.

## Limitations in Windows.Media.SpeechRecognition

* The app crashes when trying to close the application via the "X" button and the app is **Packaged**. There is an open bug report: [Application crashes after using SpeechRecognizer in a Packaged App](https://github.com/microsoft/microsoft-ui-xaml/issues/10697)

## Solutions

To use the SpeechToTextButton on WinUI, you can use one of the following approaches:

* Set the `SpeechRecognizerCreator` property of the `RadSpeechToTextButton` to `RadSpeechRecognizer` for **Unpackaged** apps:

```csharp
this.speechToTextButton.SpeechRecognizerCreator = () => new RadSpeechRecognizer();
```

* Create a [custom recognizer]({%slug speechtotextbutton-custom-recognizer%}) for **Packaged** and **Unpackaged** apps.

* Use an **Unpackaged** app deployment model.

### Configure Speech Recognition

Confirm the following are enabled in your WinUI app:

* Online speech recognition&mdash;(Settings -> Privacy -> Privacy & Security) is enabled.
* Microphone&mdash;(Settings -> Privacy & Security -> Microphone) has the necessary permissions for the app. 

### Language Support

When setting the `RadSpeechToTextButton.LanguageTag` property to a specific value, ensure that the language is supported by the `Windows.Media.SpeechRecognition.SpeechRecognizer` on WinUI. 

For more details, review the [Microsoft documentation](https://learn.microsoft.com/en-us/windows/apps/design/input/speech-recognition#predefined-grammars).

## See Also

- [Visual States in the SpeechToTextButton]({%slug speechtotextbutton-visual-states%})
- [Configure the SpeechToTextButton]({%slug speechtotextbutton-configuration%})
- [Events]({%slug speechtotextbutton-events%})
- [Execute Commands]({%slug speechtotextbutton-commands%})