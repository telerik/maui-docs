---
title: Ticks
page_title: .NET MAUI CircularSlider Documentation - Ticks
description: Learn how to configure the ticks of the Telerik UI CircularSlider for .NET MAUI. Choose where to place the ticks and choose if your slider will snap to them.
position: 8
slug: circularslider-ticks
---

# .NET MAUI CircularSlider Ticks

The CircularSlider for .NET MAUI can show ticks along the backtrack. Ticks help end users to more easily identify the selected value.

## Ticks Step and Placement

To display ticks along the arc, define the `TickStep` and `TicksPlacement` properties of the CircularSlider.

* `TickStep` (`double`)&mdash;Defines the values on the backtrack that are indicated by ticks. Each tick is placed at the specified value interval. For example, if `TickStep="5"`, your ticks are placed on the 0, 5, 10, 15, and 20 positions on a 0-20 backtrack.
* `TickOrigin` (`double`)&mdash;Defines a custom value that indicates where the ticks originate. The position of the ticks is determined based on the combination of the `TickStep` and `TickOrigin` values. The CircularSlider generates the ticks and labels in a way so that a tick is positioned at the given `TickOrigin`.
* `TicksPlacement` (`Telerik.Maui.Controls.RangeSlider.SliderTicksPlacement`)&mdash;Defines where the ticks are displayed relative to the position of the backtrack. The available options are:
    * `None`&mdash;No ticks are displayed.
    * `Start`&mdash;The ticks appear on the inner side of the arc.
    * `Center`&mdash;The ticks overlay the arc.
    * `End`&mdash;The ticks appear on the outer side of the arc.

## CircularSlider SnapMode

The CircularSlider for .NET MAUI provides snapping to ticks (the thumb snaps from tick to tick, ignoring the values in-between). This limits the selected `Value` to a predefined set of values related to the `TickStep` value. You can enable or disable snapping with the `SnapMode` property:

* `SnapMode` (`Telerik.Maui.Controls.RangeSlider.SliderSnapMode`)&mdash;Defines whether the thumb should snap to a tick, ignoring the values between ticks. The available options are:
    * `None`&mdash;The end user can move the dragged thumb freely.
    * `SnapToTicks`&mdash;The thumb is snapped to the position of the ticks when an end user is dragging it.

The snippet below shows how to apply the ticks configuration settings:

<snippet id='circularslider-ticks-settings' />

![Telerik CircularSlider for .NET MAUI Ticks](images/circularslider-ticks-settings.png)

## Tick Template

Through the `TickTemplate` property you can customize the appearance of the ticks.

* `TickTemplate` (`DataTemplate`)&mdash;Defines the template of the CircularSlider ticks.

Check below a sample `TickTemplate` example:

1. First define the custom `DataTemplate`:

<snippet id='circularslider-ticks-ticktemplate-datatemplate' />

2. Then apply it to the CircularSlider's `TickTemplate`:

<snippet id='circularslider-ticks-ticktemplate-xaml' />

3. Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

![Telerik CircularSlider for .NET MAUI Ticks Template](images/circularslider-ticks-template.png)

## See Also

- [Labels]({% slug circularslider-labels%})
- [Ticks Styling]({% slug circularslider-ticks-styling%})
