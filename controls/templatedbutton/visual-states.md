---
title: Visual States
page_title: .NET MAUI TemplatedButton Documentation - Visual States
description: Learn how to set the border color, border thickness and other in different Visual States of the Telerik TemplatedButton for .NET MAUI.
position: 9
tags: .net maui, telerik .net maui, ui for .net maui, templated, button, microsoft .net maui
slug: templatedbutton-visual-states
---

# .NET MAUI TemplatedButton Visual States

The TemplatedButton provides the following visual states described in the table below:

| Visual States | Description |
| ------------- | --------------- |
| `Normal` | Applies when the button is in normal state |
| `Pressed` | Applies when the button is pressed |
| `PointerOver` | Applies when the mouse pointer hovers over the control - applicable for Desktop |
| `Disabled` | Applies when the button is disabled |

### Using the Visual States

The following example demonstrates how to use the TemplatedButton Visual States.

**1.** Define the TemplatedButton in XAML:

<snippet id='templatedbutton-visual-states' />

**2.** Define the Visual States in the page's resources:

<snippet id='templatedbutton-visual-states-resources' />

**3.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

> For a runnable example demonstrating the TemplatedButton Visual States, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **TemplatedButton > Features** category.

## See Also

- [Configure the TemplatedButton]({%slug templatedbutton-contenfiguration%})
- [Loading Button]({%slug templatedbutton-loading-button%})
- [Events]({%slug templatedbutton-events%})
- [Execute Command]({%slug templatedbutton-command%})
- [Style the TemplatedButton]({%slug templatedbutton-styling%})