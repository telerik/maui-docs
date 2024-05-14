---
title: Input View
page_title: .NET MAUI AIPrompt Documentation - Input View
description: Learn more about the input view in the Telerik UI for .NET MAUI AIPrompt control.
position: 1
slug: aiprompt-input-view
---

# Input View

The Input view features the input editor, where users can type their query. It also contains a button to trigger a response request.

Additionally, the Input view can display suggestions related to the input itself. To control these suggestions, use the `Suggestions` collection. The user can select any of the available suggestions, which in turn will populate the input editor with the selected suggestion. This interaction will not trigger a response request right away&mdash;the user can modify the suggestion first.

>For more details on the Suggestions feature, go to the  [Suggestions]({%slug aiprompt-suggestions%}) topic.

The Input View is represented by the `AIPromptInputView` class and provides the following properties:

* `InputText`(`string`)&mdash;Defines the input used for generating a response.
* `PromptRequestCommand`(`ICommand`)&mdash;Defines a command that is executed when the end-user makes a request by pressing the input button.

> You can also apply `InputText` and `PromptRequestCommand` directly to the `RadAIPrompt` instance - for an example, check the [Views]({%slug aiprompt-views-overview%}) topic.


Here is an example of a simple `AIPromptInputView`:

<snippet id='aiprompt-inputoutputview-xaml' />

and the referenced `ViewModel` class:

<snippet id='aiprompt-views-viewmodel' />

## See Also

- [Views]({%slug aiprompt-views-overview%})
- [Suggestions]({%slug aiprompt-suggestions%})
- [Output View]({%slug aiprompt-output-view%})
