---
title: Visual States
page_title: .NET MAUI ToggleButton Documentation - Visual States
description: Learn how to set the border color, border thickness and other in different Visual States of the Telerik ToggleButton for .NET MAUI.
position: 9
tags: .net maui, telerik .net maui, ui for .net maui, toggle, button, microsoft .net maui
slug: togglebutton-visual-states
---

# .NET MAUI ToggleButton Visual States

The ToggleButton provides the following `CommonStates` visual states described in the table below:

| Visual States | Description |
| ------------- | --------------- |
| `Normal` | Applies when the button is in normal state |
| `Pressed` | Applies when the button is pressed |
| `MouseOver` | Applies when the mouse pointer hovers over the control - applicable for Desktop |
| `Disabled` | Applies when the button is disabled |
| `Toggled` | Applies when the button is disabled |
| `ToggledMouseOver` | Applies when the button is disabled |
| `ToggledPressed` | Applies when the button is disabled |
| `ToggledDisabled` | Applies when the button is disabled |
| `Indeterminate` | Applies when the button is disabled |
| `IndeterminateMouseOver` | Applies when the button is disabled |
| `IndeterminatePressed` | Applies when the button is disabled |
| `IndeterminateDisabled` | Applies when the button is disabled |

The ToggleButton provides the following `FocusStates` visual states described in the table below:

| Visual States | Description |
| ------------- | --------------- |
| `Unfocused` | Applies when the button is in normal state |
| `Focused` | Applies when the button is pressed |

### Using the Visual States

The following example demonstrates how to use the ToggleButton Visual States.

**1.** Define the ToggleButton in XAML:

<snippet id='togglebutton-visual-states' />

**2.** Define the Visual States in the page's resources:

<snippet id='togglebutton-visual-states-resources' />

**3.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

> For a runnable example demonstrating the ToggleButton Visual States, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **ToggleButton > Features** category.

## See Also

- [Configure the ToggleButton]({%slug togglebutton-contenfiguration%})
- [Toggle State]({%slug togglebutton-toggle-states%})
- [Apply Ripple Effect]({%slug togglebutton-ripple%})
- [Events]({%slug togglebutton-events%})
- [Execute Command]({%slug togglebutton-command%})
- [Style the ToggleButon]({%slug togglebutton-styling%})
