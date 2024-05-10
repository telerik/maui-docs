---
title: Ripple
page_title: .NET MAUI TemplatedButton Documentation - Ripple Effect
description: Learn how to apply ripple effect to the Telerik TemplatedButton for .NET MAUI.
position: 10
published: False
tags: .net maui, telerik .net maui, ui for .net maui, templated, button, microsoft .net maui, ripple
slug: templatedbutton-ripple
---

# .NET MAUI TemplatedButton Ripple Effect

By using attached properties you can apply a ripple effect to the TemplatedButton.

The `Ripple` class exposes the following properties:

* `Color` (`Color`)&mdash;Specifies the color of the ripple effect.
* `Mode` (enum of type `Telerik.Maui.Theming.RippleMode`)&mdash;Specifies the mode in which the ripple effect can be visualized. The options are `None`, `Pulse`, `Hold`.

### Using the Ripple

The following example demonstrates how to apply ripple effect to the TemplatedButton.

**1.** Define the buttons in XAML:

<snippet id='templatedbutton-ripple-effect' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

> For a runnable example demonstrating the TemplatedButton Ripple Effect, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **TemplatedButton > Features** category.

## See Also

- [Configure the TemplatedButton]({%slug templatedbutton-contenfiguration%})
- [Loading Button]({%slug templatedbutton-loading-button%})
- [Set Visual States]({%slug templatedbutton-visual-states%})
- [Events]({%slug templatedbutton-events%})
- [Execute Command]({%slug templatedbutton-command%})
- [Style the ToggleButon]({%slug templatedbutton-styling%})
