---
title: Events
page_title: .NET MAUI SpeechToTextButton Documentation - Events
description: Learn about the events that the SpeechToTextButton for .NET MAUI exposes.
position: 8
tags: .net maui, telerik speech to text button for .net maui, ui for .net maui
slug: speechtotextbutton-events
---

# .NET MAUI SpeechToTextButton Events

The .NET MAUI SpeechToTextButton emits a set of events that allow you to configure the component's behavior in response to speech recognition.

The .NET MAUI SpeechToTextButton exposes the following events:

* `SpeechRecognized`&mdash;Raised when the speech recognition is successful and the recognized text is available. The `SpeechRecognized` event handler receives two parameters:
	* The `sender` argument which is of type `object` but can be cast to `RadSpeechToTextButton`.
	* A `SpeechRecognizerSpeechRecognizedEventArgs` argument which has a reference to the:
		* `FullText` (`string`) property that contains the current full text recognized from the speech input.
		* `FullTextConfidenceScore` property that indicates the confidence level of the recognition. The value is between 0 and 1, indicating how confident the speech-to-text transcription is. If the value is -1, a confidence score could not be provided.

* `ErrorOccurred`&mdash;Raised when an error occurs during the speech recognition process. The `ErrorOccurred` event handler receives two parameters:
	* The `sender` argument which is of type `object` but can be cast to `RadSpeechToTextButton`.
	* A `SpeechRecognizerErrorOccurredEventArgs` argument which has a reference to the:
		* `Message` (`string`) property that contains the error message describing the issue that occurred during speech recognition.
		* `Exception` (`System.Exception`) property that contains the exception associated with the speech recognizer error, if any.
		* `Handled` (`bool`) property that determines whether the error has been handled. Set this to `true` to prevent the default error handling behavior.

* `StateChanged`&mdash;Raised when the state of the speech recognizer changes. The `StateChanged` event handler receives two parameters:
	* The `sender` argument which is of type `object` but can be cast to `RadSpeechToTextButton`.
	* An `System.EventArgs`.

## Example

Here is an example using the `SpeechRecognized` and `ErrorOccurred` events:

**1.** Define the `SpeechToTextButton` in XAML:

<snippet id='speechtotext-events' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Handle the `SpeechRecognized` event:

<snippet id='speechtotext-events-speech-recognized' />

**4.** Handle the `ErrorOccurred` event:

<snippet id='speechtotext-events-error-occured' />

> For a runnable example with the SpeechToTextButton Events scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **SpeechToTextButton > Features** category.

## See Also

- [Set Visual States]({%slug speechtotextbutton-visual-states%})
- [Custom Recognizer]({%slug speechtotextbutton-custom-recognizer%})
- [Execute Commands]({%slug speechtotextbutton-commands%})
- [Style the SpeechToTextButton]({%slug speechtotextbutton-styling%})