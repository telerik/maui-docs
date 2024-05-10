---
title: Command
page_title: .NET MAUI ToggleButton Documentation - Command
description: Review ToggleButton Command that is executed when button is clicked. 
position: 8
slug: togglebutton-command
---

# .NET MAUI ToggleButton Commands

The Telerik .NET MAUI ToggleButton allows you to attach a command that executes when the button is clicked.

* `Command` (`ICommand`)&mdash;Defines the command, which executes when the button is clicked.
* `CommandParameter` (`object`)&mdash;Specifies the parameter of the command, which executes when the button is clicked.

## Using the Command and CommanParameter

The following example demonstrates how to use the `Command`:

**1.** Define the ToggleButton in XAML:

<snippet id='togglebutton-command-xaml' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Add the `ViewModel`:

<snippet id='togglebutton-command-viewmodel' />

> For a runnable example demonstrating the ToggleButton Command, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **ToggleButton > Features** category.

## See Also

- [Configure the ToggleButton]({%slug togglebutton-contenfiguration%})
- [Toggle State]({%slug togglebutton-toggle-states%})
- [Apply Ripple Effect]({%slug togglebutton-ripple%})
- [Set Visual States]({%slug togglebutton-visual-states%})
- [Events]({%slug togglebutton-events%})
- [Style the ToggleButton]({%slug togglebutton-styling%})