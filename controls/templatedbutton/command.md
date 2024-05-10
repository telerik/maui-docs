---
title: Command
page_title: .NET MAUI TemplatedButton Documentation - Command
description: Review TemplatedButton Command that is executed when button is clicked. 
position: 8
slug: templatedbutton-command
---

# .NET MAUI TemplatedButton Commands

The Telerik .NET MAUI TemplatedButton allows you to attach a command that executes when the button is clicked.

* `Command` (`ICommand`)&mdash;Defines the command, which executes when the button is clicked.
* `CommandParameter` (`object`)&mdash;Specifies the parameter of the command, which executes when the button is clicked.

## Using the Command

The following example demonstrates how to use the `Clicked` event:

**1.** Define the TemplatedButton in XAML:

<snippet id='templatedbutton-command-xaml' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Add the `ViewModel`:

<snippet id='templatedbutton-command-viewmodel' />

> For a runnable example demonstrating the TemplatedButton Command, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **TemplatedButton > Features** category.

## See Also

- [Configure the TemplatedButton]({%slug templatedbutton-contenfiguration%})
- [Loading Button]({%slug templatedbutton-loading-button%})
- [Set Visual States]({%slug templatedbutton-visual-states%})
- [Events]({%slug templatedbutton-events%})
- [Style the TemplatedButton]({%slug templatedbutton-styling%})