---
title: Visual States
page_title: .NET MAUI TemplatedButton Documentation - Visual States
description: Learn how to set the border color, border thickness and other for the different visual states of the Telerik TemplatedButton for .NET MAUI.
position: 9
tags: .net maui, telerik .net maui, ui for .net maui, templated, button, microsoft .net maui
slug: templatedbutton-visual-states
---

# .NET MAUI TemplatedButton Visual States

The TemplatedButton provides the following `CommonStates` visual states:

| Visual States | Description |
| ------------- | --------------- |
| `Normal` | Applies when the button is in normal state. |
| `Pressed` | Applies when the button is pressed. |
| `PointerOver` | (Desktop-only) Applies when the mouse pointer hovers over the control. |
| `Disabled` | Applies when the button is disabled. |

## Using the Visual States

The following example demonstrates how to use the TemplatedButton visual states.

**1.** Define the TemplatedButton in XAML:

<snippet id='templatedbutton-visual-states' />

**2.** Define the visual states in the page's resources:

<snippet id='templatedbutton-visual-states-resources' />

**3.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

This is the result on WinUI:

![.NET MAUI TemplatedButton Visual States](images/templatedbutton-visualstates.gif "TemplatedButton for .NET MAUI")

> For a runnable example demonstrating the TemplatedButton visual states, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **TemplatedButton > Features** category.

## See Also

- [Configure the TemplatedButton]({%slug templatedbutton-configuration%})
- [Loading Button]({%slug templatedbutton-loading-button%})
- [Events]({%slug templatedbutton-events%})
- [Execute Command]({%slug templatedbutton-command%})
- [Style the TemplatedButton]({%slug templatedbutton-styling%})