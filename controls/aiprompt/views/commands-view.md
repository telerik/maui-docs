---
title: Commands View
page_title: .NET MAUI AIPrompt Documentation - Commands View
description: Learn more about the commands view in the Telerik UI for .NET MAUI AIPrompt control.
position: 3
slug: aiprompt-commands-view
---

# Commands View

The Commands View displays a set of predefined commands, which the user can browse and execute. The commands are passed to the component through the `Commands` property, which expects a collection of `AIPromptCommandBase` objects.

The Commands View is represented by the `AIPromptCommandView` class and provides the following properties:

* `Commands`(`IList<AIPromptCommandBase>`)&mdash;Defines a list of AIPrompt commands.
* `CommandTappedCommand`(`ICommand`)&mdash;Defines a command that is executed an AIPrompt command is pressed.

>For more details on how you can define a `AIPromptCommand`, go to the [Commands]({%slug aiprompt-commands%}) topic.

Here is an example of a simple `AIPromptCommandView`:

<snippet id='aiprompt-commands-xaml' />

and the referenced `ViewModel` class:

<snippet id='aiprompt-views-viewmodel' />

## See Also

- [Views]({%slug aiprompt-views-overview%})
- [Commands]({%slug aiprompt-commands%})
- [Output View]({%slug aiprompt-output-view%})
