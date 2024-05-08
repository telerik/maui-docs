---
title: Styling
page_title: .NET MAUI TemplatedButton Documentation - Styling
description: Learn how to set the border color, border thickness and other styling properties of the Telerik TemplatedButton for .NET MAUI.
position: 3
tags: .net maui, telerik .net maui, ui for .net maui, templated, button, microsoft .net maui
slug: templatedbutton-styling
---

# .NET MAUI TemplatedButton Styling

The TemplatedButton provides a set of styling options by exposing properties for customizing its visual appearance.

## Stling the TemplatedButton

To style the TemplatedButton, use the following properties:

* `Background` (`Brush`)&mdash;Specifies the background brush of the control.
* `BackgroundColor` (`Color`)&mdash;Specifies the background color of the control.
* `BorderColor` (`Color`)&mdash;Specifies the border color of the control.
* `BorderBrush` (`Brush`)&mdash;Specifies the border brush of the control.
* `BorderThickness` (`Thickness`)&mdash;Specifies the border thickness of the control.
* `CornerRadius` (`CornerRadius`)&mdash;Specifies the corner radius of the control.
* `Padding` (`Thickness`)&mdash;Specifies the padding of the control.
* `TextColor` (`Color`)&mdash;Specifies the color of the `Label.Text` created when `Content` is `string` and `ContentTemplate` is not set.

### Using the Styling API

The following example demonstrates how to apply implicit and explicit styles to the TemplatedButton.

**1.** Define the buttons in XAML:

<snippet id='templatedbutton-styling' />

**2.** Define the explicit styling to the page's resources:

<snippet id='templatedbutton-styling-explicit' />

**3.** Define the implicit styling to the page's resources:

<snippet id='templatedbutton-styling-implicit' />

**4.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

> For a runnable example demonstrating the TemplatedButton Styling options, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **TemplatedButton > Styling** category.

## Visual States

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

## Ripple Effect

By using attached properties you can apply a ripple effect to the TemplatedButon.

The `Ripple` class exposes two properties:

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

- [Creating a Loading Button]({%slug templatedbutton-loading-button%})
