---
title: Command
page_title: .NET MAUI TemplatedButton Documentation - Command
description: Learn about the .NET MAUI TemplatedButton Command that is executed when the button is clicked.
position: 8
slug: templatedbutton-command
---

# .NET MAUI TemplatedButton Command

The Telerik .NET MAUI TemplatedButton allows you to attach a command that executes when the button is clicked or tapped.

* `Command` (`ICommand`)&mdash;Defines the command which executes when the button is clicked or tapped.
* `CommandParameter` (`object`)&mdash;Specifies the parameter of the command which executes when the button is clicked or tapped.

## Using the Command

The following example demonstrates how to use the `Command` to change the text displayed within the ToggledButton on click.

**1.** Define the TemplatedButton in XAML:

<snippet id='templatedbutton-command-xaml' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Add the `ViewModel`:

<snippet id='templatedbutton-command-viewmodel' />

This is the result on WinUI:

![.NET MAUI TemplatedButton Command](images/templatedbutton-command.gif "TemplatedButton for .NET MAUI")

> For a runnable example demonstrating the TemplatedButton Command, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **TemplatedButton > Features** category.

## See Also

- [Configure the TemplatedButton]({%slug templatedbutton-configuration%})
- [Loading Button]({%slug templatedbutton-loading-button%})
- [Set Visual States]({%slug templatedbutton-visual-states%})
- [Events]({%slug templatedbutton-events%})
- [Style the TemplatedButton]({%slug templatedbutton-styling%})