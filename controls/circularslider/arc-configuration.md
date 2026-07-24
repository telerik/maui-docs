---
title: Arc Configuration
page_title: .NET MAUI CircularSlider Documentation - Arc Configuration
description: Learn how to configure the circular arc of the Telerik UI for .NET MAUI CircularSlider through the start angle, sweep angle, sweep direction, radius factor, and size.
position: 4
slug: circularslider-arc-configuration
---

# .NET MAUI CircularSlider Arc Configuration

The CircularSlider for .NET MAUI draws its backtrack along a circular arc. You can control the shape, length, direction, and size of that arc through a set of dedicated properties.

## Arc Angles and Direction

Use the following properties to define the position and length of the arc:

* `StartAngle` (`double`)&mdash;Specifies the angle from which the arc starts. Regardless of the `SweepDirection`, the start angle is treated as in trigonometry&mdash;a positive rotation is a counter-clockwise rotation.
* `SweepAngle` (`double`)&mdash;Specifies the angle that defines the length of the arc. When the `SweepAngle` is `360`, the CircularSlider forms a full circle.
* `SweepDirection` (`Microsoft.Maui.Controls.Shapes.SweepDirection`)&mdash;Specifies the sweep direction of the arc. The value of this property does not affect the direction of the start angle. The available options are:
    * `Clockwise`&mdash;The arc sweeps in a clockwise direction.
    * `Counterclockwise`&mdash;The arc sweeps in a counter-clockwise direction.

The following example shows how to configure a partial arc:

<snippet id='circularslider-arc-settings' />

## Radius Factor

The `RadiusFactor` property controls how much of the available space the arc occupies.

* `RadiusFactor` (`double`)&mdash;Specifies the radius factor that controls the size of the circular arc relative to the available space. The value must be between `0.1` and `1.0`, where `1.0` means the arc fills the entire available space and `0.1` means the arc is very small. The default value is `0.7`.

<snippet id='circularslider-radius-factor' />

## Size

The CircularSlider defines default minimum dimensions so that the arc, ticks, and labels remain readable. You can override these dimensions:

* `MinimumHeightRequest` (`double`)&mdash;Specifies the minimum height of the control.
* `MinimumWidthRequest` (`double`)&mdash;Specifies the minimum width of the control.

> For a runnable example with the CircularSlider arc configuration scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **CircularSlider > Features** category.

## See Also

- [Value Thumb]({% slug circularslider-value-thumb%})
- [Labels]({% slug circularslider-labels%})
