---
title: Visual States
page_title: .NET MAUI ToggleButton Documentation - Visual States
description: Learn how to set the border color, border thickness and other in the different visual states of the Telerik ToggleButton for .NET MAUI.
position: 9
tags: .net maui, telerik .net maui, ui for .net maui, toggle, button, microsoft .net maui
slug: togglebutton-visual-states
---

# .NET MAUI ToggleButton Visual States

The ToggleButton provides the following `CommonStates` visual states:

| Visual State | Description |
| ------------- | --------------- |
| `Normal` | Applies when the button is in normal state. |
| `Pressed` | Applies when the button is pressed. |
| `MouseOver` | (Desktop-only) Applies when the mouse pointer hovers over the control. |
| `Disabled` | Applies when the button is disabled. |
| `Toggled` | Applies when the button is toggled. |
| `ToggledMouseOver` | (Desktop-only) Applies when the button is toggled and the mouse is over the button. |
| `ToggledPressed` | Applies when the button is toggled and pressed. |
| `ToggledDisabled` | Applies when the button is toggled and disabled. |
| `Indeterminate` | Applies when the button is in an indeterminate state. |
| `IndeterminateMouseOver` | (Desktop-only) Applies when the button is in an indeterminate state and the mouse is over the button. |
| `IndeterminatePressed` | Applies when the button is in an indeterminate state and pressed. |
| `IndeterminateDisabled` | Applies when the button is in an indeterminate state and disabled. |

The ToggleButton provides the following `FocusStates` visual states:

| Visual States | Description |
| ------------- | --------------- |
| `Unfocused` | Applies when the button is in normal state. |
| `Focused` | Applies when the button is pressed. |

### Using the Visual States

The following example demonstrates how to use the ToggleButton Visual States.

**1.** Define the ToggleButton in XAML:

<snippet id='togglebutton-visual-states' />

**2.** Define the visual states in the page's resources:

<snippet id='togglebutton-visual-states-resources' />

**3.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

This is the result on WinUI: 

![.NET MAUI ToggleButton Visual States](images/togglebutton-visualstates.gif)

>tip For a runnable example demonstrating the ToggleButton visual state, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **ToggleButton > Features** category.

## See Also

- [Configure the ToggleButton]({%slug togglebutton-configuration%})
- [Toggle State]({%slug togglebutton-toggle-states%})
- [Events]({%slug togglebutton-events%})
- [Execute Command]({%slug togglebutton-command%})
- [Style the ToggleButton]({%slug togglebutton-styling%})
