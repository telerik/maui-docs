---
title: Visual States
page_title: .NET MAUI DropDownButton Documentation - Visual States
description: Learn how to set the border color, border thickness and other styling options for the different visual states of the Telerik DropDownButton for .NET MAUI.
position: 10
tags: .net maui, telerik .net maui, ui for .net maui, templated, button, microsoft .net maui
slug: dropdownbutton-visual-states
---

# .NET MAUI DropDownButton Visual States

This article describes the visual states the DropDownButton provides. 
You can use the visual states to change the visual appearance of the control depending on the state the control is set&mdash;whether it's disabled, or pressed, or has the mouse pointer over.

The DropDownButton provides the following `CommonStates` visual states:

| Visual States | Description |
| ------------- | --------------- |
| `Normal` | Applies when the button is in normal state. |
| `Opened` | Applies when the drop-down is opened. |
| `Pressed` | Applies when the button is pressed. |
| `FocusedPressed` | (Desktop-only) Applies when the button is pressed and focused by the keyboard. |
| `MouseOver` | (Desktop-only) Applies when the mouse pointer hovers over the control. |
| `FocusedMouseOver` | (Desktop-only) Applies when the mouse pointer hovers over the control and the control is focused by the keyboard. |
| `Disabled` | Applies when the button is disabled. |

## Using the Visual States

The following example demonstrates how to use the DropDownButton visual states.

**1.** Define the DropDownButton in XAML:

<snippet id='dropdownbutton-buttonstyling-apply' />

**2.** Define the visual states in the page's resources:

<snippet id='dropdownbutton-buttonstyling-styles' />

**3.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

> For a runnable example demonstrating the DropDownButton visual states, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **DropDownButton > Styling** category.

## See Also

- [Configure the Button Content and Indicator]({%slug dropdownbutton-configuration%})
- [Configure the Drop-Down Part]({%slug dropdownbutton-drop-down-configuration%})
- [Style the DropDownButton]({%slug dropdownbutton-styling%})
- [Command]({%slug dropdownbutton-command%})
- [Events]({%slug dropdownbutton-events%})
- [Animation]({%slug dropdownbutton-animation%})
