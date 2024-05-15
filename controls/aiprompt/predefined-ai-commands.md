---
title: Predefined AI Commands
page_title: .NET MAUI AIPrompt Documentation - Predefined AI Commands
description: Learn more about the predefined AI Commands in the CommandsView in the Telerik UI for .NET MAUI AIPrompt control.
position: 7
slug: aiprompt-aicommands
---

# Predefined AI Commands

The AIPrompt exposes the `Commands` collection. It allows you to provide a collection of objects deriving from the `AIPromptCommandBase` class that will be displayed in the Commands View of the component.

The `AIPromptCommandBase` class provides the following properties:

* `ImageSource`(`ImageSource`)&mdash;Allows you to display an icon for the command in the Commands View of the AIPrompt control.
* `Text`(`string`)&mdash;Allows you to specify a string that will display information about the command.

In addition, you can use the `AIPromptCommand` class which inherits from `AIPromtCommandBase` and provides additional `Command` property:

* `Command`(`ICommand`)&mdash;Defines the command that is executed when the AIPrompt command is tapped.

You can use three different approaches to add a logic that will be executed when the user interacts with the Commands View's items. All are listed below according to their precedence.

### Using `AIPromptCommand`'s `Command` property

Let's, for example, add the following `AIPromptCommand` to `Commands` collection:

```C#
 this.Commands.Add(new AIPromptCommand
  {     mageSource = new FontImageSource() { FontFamily = TelerikFont.Name, Size = 12, Glyph = TelerikFont.IconPaste}, 
        Text = "Simplify", 
        Command = this.CheckSyntaxCommand });
this.CheckSyntaxCommand = new Command(this.ExecuteCheckSyntaxCommand);
```

where `ExecuteCheckSyntaxCommand` is defined like this:

```C#
private void ExecuteCheckSyntaxCommand(object arg)
{
    Application.Current.MainPage.DisplayAlert("executing", "check for syntax errors command", "close");
}
```

In case the `AIPromptCommand` has `Command` applied, that `Command` will be executed when the corresponding command item in the Commands View is tapped.

### Using the `RadAIPrompt`'s `CommandTappedCommand`

In case the `AIPromptCommand`'`Command` is null, the AIPrompt's `CommandTappedCommand` will be executed:

```C#
 this.Commands.Add(new AIPromptCommand
  {     mageSource = new FontImageSource() { FontFamily = TelerikFont.Name, Size = 12, Glyph = TelerikFont.IconPaste}, 
        Text = "Simplify"});
this.CommandTappedCommand = new Command(this.ExecuteCommandTappedCommand);
```

### Using the `RadAIPrompt`'`PromptRequestCommand`

In case neither the `AIPromptCommand`'`Command` is null nor the `CommandTappedCommand` is provided, and the Command View's items are tapped, the `InputText` is updated to the `AIPromptCommand`'`Text` and the `RadAIPrompt`'`PromptRequestCommand` is executed.

>For more information on how to define and execute ai commands, go to [Commands View]({%slug aiprompt-commands-view%}) topic.

## See Also

- [Views]({%slug aiprompt-views-overview%})
- [Commands View]({%slug aiprompt-commands-view%})
