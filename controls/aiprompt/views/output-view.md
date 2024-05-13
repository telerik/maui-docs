---
title: Output View
page_title: .NET MAUI AIPrompt Documentation - Output View
description: Learn more about the output view in the Telerik UI for .NET MAUI AIPrompt control.
position: 2
slug: aiprompt-output-view
---

# Output View

The Output view shows the responses generated by the underlying AI service. Each response renders in its dedicated output item and provides two options to the user—to copy the content of the response or to retry the request. The Output view is activated through interaction—once the user fills out a prompt within the Input view and requests a response, the Output view will become active.

Each output item will also feature two additional options-to upvote or downvote the response. To handle this interaction, you can use the `OutputItemRatingChangedCommand` command.

The output view is represented by the `AIPromptOutputView` class and provides the following properties:

* `OutputItems`(`IList<AIPromptOutputItem>`)&mdash;Defines a collection of the generated response items.
* `OutputItemCopyCommand`(`ICommand`)&mdash;Defines a command executed when the copy button of the generated response item is pressed.
* `OutputItemRetryCommand`(`ICommand`)&mdash;Defines a command executed when the retry button of the generated response item is pressed.
* `OutputItemRatingChangedCommand`(`ICommand`)&mdash;Defines a command executed when the rating of the generated response is changed through the UI.

Here is an example of a simple `AIPromptOutputView`:

<snippet id='aiprompt-inputoutputview-xaml' />

and the referenced `ViewModel` class:

<snippet id='aiprompt-views-viewmodel' />

## See Also

- [Views]({%slug aiprompt-views-overview%})
- [Input View]({%slug aiprompt-input-view%})