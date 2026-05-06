---
title: Command
page_title: .NET MAUI DropDownButton Documentation - Command
description: Learn about the .NET MAUI DropDownButton Command that is executed when the button is clicked.
position: 8
slug: dropdownbutton-command
---

# .NET MAUI DropDownButton Command

The Telerik .NET MAUI DropDownButton allows you to attach a command that executes when the button is clicked.

* `Command` (`ICommand`)&mdash;Defines the command which executes when the button is clicked.
* `CommandParameter` (`object`)&mdash;Specifies the parameter of the command which executes when the button is clicked.

## Using the Command

The following example demonstrates how to use the `Command` to change the text displayed within the DropDownButton on click.

**1.** Define the DropDownButton in XAML:

<snippet id='dropdownbutton-command-xaml' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Add the `ViewModel`:

<snippet id='dropdownbutton-command-viewmodel' />

This is the result on WinUI:

![.NET MAUI DropDownButton Command](images/DropDownButton-command.gif "DropDownButton for .NET MAUI")

> For a runnable example demonstrating the DropDownButton Command, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **DropDownButton > Features** category.

## See Also

- [Configure the Button Content and Indicator]({%slug dropdownbutton-configuration%})
- [Configure the Drop-Down Part]({%slug dropdownbutton-drop-down-configuration%})
- [Style the DropDownButton]({%slug dropdownbutton-styling%})
- [Events]({%slug dropdownbutton-events%})
- [Animation]({%slug dropdownbutton-animation%})
