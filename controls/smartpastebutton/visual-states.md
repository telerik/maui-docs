---
title: Visual States
page_title: .NET MAUI SmartPasteButton Documentation - Visual States
description: Learn how to set the border color, border thickness and other styling options for the different visual states of the Telerik SmartPasteButton for .NET MAUI.
position: 10
tags: .net maui, telerik .net maui, ui for .net maui, templated, button, microsoft .net maui
slug: smartpastebutton-visual-states
---

# .NET MAUI SmartPasteButton Visual States

This article describes the visual states the SmartPasteButton provides. 
You can use the visual states to change the visual appearance of the control depending on the state the control is set&mdash;whether it's disabled, or pressed, or has the mouse pointer over.

The SmartPasteButton provides the following `CommonStates` visual states:

| Visual States | Description |
| ------------- | --------------- |
| `Normal` | Applies when the button is in normal state. |
| `Pressed` | Applies when the button is pressed. |
| `MouseOver` | (Desktop-only) Applies when the mouse pointer hovers over the control. |
| `Disabled` | Applies when the button is disabled. |
| `Processing` | Applies when the button the smart paste request is in process. |
| `ProcessingPressed` | Applies when the button is pressed while the smart paste request is in process. |
| `ProcessingMouseOver` | Applies when the mouse pointer hovers over the button when the smart paste request is in process. |
| `ProcessingFocused` | Applies when the button is focused and the smart paste request in process. |

## Using the Visual States

The following example demonstrates how to use the SmartPasteButton visual states.

**1.** Define the buttons in XAML:

<snippet id='smartpastebutton-styling-implicit-xaml' />
<snippet id='smartpastebutton-styling-explicit-xaml' />

**2.** Define the explicit styling to the page's resources:

<snippet id='smartpastebutton-styling-explicit' />

**3.** Define the implicit styling to the page's resources:

<snippet id='smartpastebutton-styling-implicit' />

**4.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

This is the result on WinUI:

![.NET MAUI SmartPasteButton Styling](images/smartpastebutton-styling.gif)


>important The SmartPasteButton examples in the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) use a Telerik-hosted AI service for demonstration purposes only. 
>
>To use the smart paste functionality in your application, you must configure your own AI service.
>
>How to do that is described in the [Configuration]({%slug smartpastebutton-configuration%}) article.

> For a runnable example demonstrating the SmartPasteButton styling options, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **SmartPasteButton > Styling** category.

## See Also

- [Configure the SmartPasteButton]({%slug smartpastebutton-configuration%})
- [Styling the SmartPasteButton]({%slug smartpastebutton-styling%})
- [Events]({%slug smartpastebutton-events%})
- [Execute Command]({%slug smartpastebutton-command%})