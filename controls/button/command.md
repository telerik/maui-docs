---
title: Command
page_title: .NET MAUI Button Documentation - Command
description: Learn about the .NET MAUI Button Command that is executed when the button is clicked.
position: 4
slug: button-command
---

# .NET MAUI Button Command

The Telerik .NET MAUI Button allows you to attach a command that executes when the button is clicked.

* `Command` (`ICommand`)&mdash;Defines the command which executes when the button is clicked.
* `CommandParameter` (`object`)&mdash;Specifies the parameter of the command which executes when the button is clicked.

## Using the Command

The following example demonstrates how to use the `Command`.

**1.** Define the Button in XAML:

<snippet id='button-command-xaml' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Execute the `Command`:

<snippet id='button-command' />

This is the result on WinUI:

![.NET MAUI Button Command](images/button-command.gif "Button for .NET MAUI")

> For a runnable example demonstrating the Button Command, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **Button > Features** category.

## See Also

- [Styling the Button]({%slug button-styling%})
- [Creating a Circular Button]({%slug button-create-circle-button%})