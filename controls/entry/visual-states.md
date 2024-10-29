---
title: Visual States
page_title: .NET MAUI Entry Documentation - Visual States
description: Learn how to set the border color, background color and other in the different visual states of the Telerik Entry for .NET MAUI.
position: 9
tags: .net maui, telerik .net maui, ui for .net maui, entry, states, microsoft .net maui
slug: entry-visual-states
---

# .NET MAUI Entry Visual States

The Entry provides the following `CommonStates` visual states:

| Visual State | Description |
| ------------- | --------------- |
| `Normal` | Applies when the entry is in normal state. |
| `Focused` | Applies when the enry is focused. |
| `MouseOver` | (Desktop-only) Applies when the mouse pointer hovers over the control. |
| `Invalid` | Applies when the enry is focused. |
| `InvalidFocused` | Applies when the enry is focused. |
| `InvalidMouseOver` | (Desktop-only) Applies when the button is toggled and the mouse is over the button. |
| `ReadOnly` | Applies when the enry is focused. |
| `ReadOnlyFocused` | Applies when the enry is focused. |
| `ReadOnlyMouseOver` | (Desktop-only) Applies when the button is toggled and disabled. |
| `ReadOnlyInvalid` | Applies when the enry is focused. |
| `ReadOnlyInvalidFocused` | Applies when the enry is focused. |
| `ReadOnlyInvalidMouseOver` | (Desktop-only) Applies when the button is in an indeterminate state and pressed. |
| `Disabled` | Applies when the enry is disabled. |

### Using the Visual States

The following example demonstrates how to use the Entry Visual States.

**1.** Define the Entry in XAML:


**2.** Define the visual states in the page's resources:


**3.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

This is the result on WinUI: 

![.NET MAUI Entry Visual States](images/)

>tip For a runnable example demonstrating the Entry visual state, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **Entry > Styling** category.

## See Also

