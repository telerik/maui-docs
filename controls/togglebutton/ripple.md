---
title: Ripple
page_title: .NET MAUI ToggleButton Documentation - Ripple Effect
description: Learn how to set a ripple effect to the Telerik ToggleButton for .NET MAUI.
position: 10
published: False
tags: .net maui, telerik .net maui, ui for .net maui, toggle, button, microsoft .net maui
slug: togglebutton-ripple
---

# .NET MAUI ToggleButton Ripple Effect

By using attached properties you can apply a ripple effect to the ToggleButton.

The `Ripple` class exposes the following properties:

* `Color` (`Color`)&mdash;Specifies the color of the ripple effect.
* `Mode` (enum of type `Telerik.Maui.Theming.RippleMode`)&mdash;Specifies the mode in which the ripple effect can be visualized. The options are `None`, `Pulse`, `Hold`.

### Using the Ripple

The following example demonstrates how to apply ripple effect to the ToggleButton.

**1.** Define the buttons in XAML:

<snippet id='togglebutton-ripple-effect' />

**2.** Define the resources in the page's resources:

<snippet id='togglebutton-ripple-visual-states-resources' />

**3.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

> For a runnable example demonstrating the ToggleButton Ripple Effect, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **ToggleButton > Features** category.

## See Also

- [Configure the ToggleButton]({%slug togglebutton-configuration%})
- [Toggle State]({%slug togglebutton-toggle-states%})
- [Set Visual States]({%slug togglebutton-visual-states%})
- [Events]({%slug togglebutton-events%})
- [Execute Command]({%slug togglebutton-command%})
- [Style the ToggleButton]({%slug togglebutton-styling%})

