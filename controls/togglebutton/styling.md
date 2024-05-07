---
title: Styling
page_title: .NET MAUI ToggleButton Documentation - Styling
description: Learn how to set the border color, border thickness and other styling properties of the Telerik ToggleButton for .NET MAUI.
position: 3
tags: .net maui, telerik .net maui, ui for .net maui, toggle, button, microsoft .net maui
slug: togglebutton-styling
---

# .NET MAUI ToggleButton Styling

The ToggleButton provides a set of styling options by exposing properties for customizing its visual appearance.

To style the ToggleButton, use the following properties:

* `Background` (`Brush`)&mdash;Specifies the background brush of the control.
* `BackgroundColor` (`Color`)&mdash;Specifies the background color of the control.
* `BorderColor` (`Color`)&mdash;Specifies the border color of the control.
* `BorderBrush` (`Brush`)&mdash;Specifies the border brush of the control.
* `BorderThickness` (`Thickness`)&mdash;Specifies the border thickness of the control.
* `CornerRadius` (`CornerRadius`)&mdash;Specifies the corner radius of the control.
* `Padding` (`Thickness`)&mdash;Specifies the padding of the control.
* `TextColor` (`Color`)&mdash;Specifies the color of the `Label.Text` created when `Content` is `string` and `ContentTemplate` is not set.

## Visual States

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

## Ripple Effect

By using attached properties you can apply a ripple effect to the TemplatedButon.

The `Ripple` class exposes two properties:

* `Color` (`Color`)&mdash;Specifies the color of the ripple effect.
* `Mode` (enum of type `Telerik.Maui.Theming.RippleMode`)&mdash;Specifies the mode in which the ripple effect can be visualized. The options are `None`, `Pulse`, `Hold`.

Here is an example with Ripple aplied:



## See Also


