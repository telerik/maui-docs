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

To style the TemplatedButton, use the following properties:

* `Background` (`Brush`)&mdash;Specifies the background brush of the control.
* `BackgroundColor` (`Color`)&mdash;Specifies the background color of the control.
* `BorderColor` (`Color`)&mdash;Specifies the border color of the control.
* `BorderBrush` (`Brush`)&mdash;Specifies the border brush of the control.
* `BorderThickness` (`Thickness`)&mdash;Specifies the border thickness of the control.
* `CornerRadius` (`CornerRadius`)&mdash;Specifies the corner radius of the control.
* `Padding` (`Thickness`)&mdash;Specifies the padding of the control.
* `TextColor` (`Color`)&mdash;Specifies the color of the `Label.Text` created when `Content` is `string` and `ContentTemplate` is not set.

## Visual States

The TemplatedButton provides the following visual states described in the table below:

| Visual States | Description |
| ------------- | --------------- |
| `Normal` | Applies when the button is in normal state |
| `Pressed` | Applies when the button is pressed |
| `PointerOver` | Applies when the mouse pointer hovers over the control - applicable for Desktop |
| `Disabled` | Applies when the button is disabled |

## Ripple Effect

By using attached properties you can apply a ripple effect to the TemplatedButon.

The `Ripple` class exposes two properties:

* `Color` (`Color`)&mdash;Specifies the color of the ripple effect.
* `Mode` (enum of type `Telerik.Maui.Theming.RippleMode`)&mdash;Specifies the mode in which the ripple effect can be visualized. The options are `None`, `Pulse`, `Hold`.

Here is an example with Ripple aplied:


## See Also

- [Creating a Loading Button]({%slug templatedbutton-loading-button%})
