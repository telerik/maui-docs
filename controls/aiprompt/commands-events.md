---
title: Commands & Events
page_title: .NET MAUI AIPrompt Documentation - Commands & Events
description: Learn more about the commands and events in the Telerik UI for .NET MAUI AIPrompt control.
position: 8
slug: aiprompt-commands-events
---

# Commands & Events

The .NET MAUI AIPrompt provides several commands that you can utilize when working with the component.

The following list shows the commands that are exposed by the AIPrompt control:

* `PromptRequestCommand`(`ICommand`)&mdash;Executed when the end-user makes a request by pressing the input button inside the Input View.
* `OutputItemCopyCommand`(`ICommand`)&mdash;Executed when the copy button of the generated response item is pressed.
* `OutputItemRetryCommand`(`ICommand`)&mdash;Executed when the retry button of the generated response item is pressed
* `OutputItemRatingChangedCommand`(`ICommand`)&mdash;Executed when the rating of the generated response is changed through the UI.
* `CommandTappedCommand`(`ICommand`)&mdash;Executed when an AIPrompt command is pressed. 

In addition, the AIPrompt exposes `PromptRequest` event:

* `PromptRequest`&mdash;Occurs when the end-user makes a request by pressing the input button inside the Input View. The `PromptRequest` event handler receives two parameters:
	- The `sender` which is the `RadAIPrompt` control.
	- `System.EventArgs`object.

## See Also

- [Views]({%slug aiprompt-views-overview%})
- [Input View]({%slug aiprompt-input-view%})
- [Output View]({%slug aiprompt-output-view%})
