---
title: Commands
page_title: .NET MAUI AIPrompt Documentation - Commands
description: Learn more about the commands in the Telerik UI for .NET MAUI AIPrompt control.
position: 7
slug: aiprompt-commands
---

# Commands

The .NET MAUI AIPrompt provides several commands that you can utilize when working with the component. Furthermore, it allows you to define custom commands that will be displayed in a separate view to further personalize the control.

The following list shows the commands that are exposed by the AIPrompt control:

* `PromptRequestCommand`(`ICommand`)&mdash;Executed when the end-user makes a request by pressing the input button.
* `OutputItemCopyCommand`(`ICommand`)&mdash;Executed when the copy button of the generated response item is pressed.
* `OutputItemRetryCommand`(`ICommand`)&mdash;Executed when the retry button of the generated response item is pressed
* `CommandTappedCommand`(`ICommand`)&mdash;Executed when an AIPrompt command is pressed.
* `OutputItemRatingChangedCommand`(`ICommand`)&mdash;Executed when the rating of the generated response is changed through the UI.

## Configuring Custom Commands

The AIPrompt exposes the `Commands` collection. It allows you to provide a collection of objects deriving from the `AIPromptCommandBase` class that will be displayed in the commands view of the component.

The `AIPromptCommandBase` class provides the following properties:

* `ImageSource`(`ImageSource`)&mdash;Allows you to display an icon for the command in the Commands View of the AIPrompt control.
* `Text`(`string`)&mdash;Allows you to specify a string that will display information about the command.

In addition, you can use the `AIPromptCommand` class which inherits from `AIPromtCommandBase` and provides additional `Command` property:

* `Command`(`ICommand`)&mdash;Defines the command that is executed when the AIPrompt command is tapped.
	
To add a logic that will be executed when the user interacts with the Commands View's items, the RadAIPrompt provides the `CommandTappedCommand` command.

>For more information on how to define and execute custom commands, go to [Commands View]({%slug aiprompt-commands-view%}) topic.

## See Also

- [Views]({%slug aiprompt-views-overview%})
- [Commands View]({%slug aiprompt-commands-view%})
