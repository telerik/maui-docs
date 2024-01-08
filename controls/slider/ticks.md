---
title: Ticks
page_title: .NET MAUI Slider Documentation - Ticks
description: Learn how to use the ticks that Telerik UI Slider for .NET MAUI control provides.
position: 5
slug: slider-ticks
---

# Ticks

The Slider for .NET MAUI can show ticks along the track in order to enable users to easily identify the Slider value.

## Ticks Step and Placement

To display ticks along the track, define `TickStep` and `TickPlacement` properties of the Slider.

* `TickStep`(`double`)&mdash;Defines at what positions/values ticks will be displayed.
* `TicksPlacement`(`Telerik.Maui.Controls.RangeSlider.SliderTicksPlacement`)&mdash;Specifies the position of the ticks in the Slider with respect to its track. The available options are:
    * `None`&mdash;no ticks are displayed.
    * `Start`&mdash;ticks appear above the track.
    * `Center`&mdash;ticks appear in the track area of the slider, overlaying the track.
    * `End`&mdash;ticks appear below the track.

## Slider SnapMode

Slider for .NET MAUI provides snapping to ticks thus limiting its `Value` to a predefined set of values depending on `TickStep` value. You can control whether the snapping is enabled through `SnapMode` property:

* `SnapMode`(`Telerik.Maui.Controls.RangeSlider.SliderSnapMode`)&mdash;Defines whether a value should be snapped to a tick while the end-user is dragging the thumb. Available options are:
    * `None`&mdash;The end user can move the dragged thumb freely.
    * `SnapToTicks`&mdash;The thumb is snapped to the position of the ticks when an end-user is dragging it.

The snippet below shows how the ticks configuration settings can be applied:

<snippet id='slider-ticks-settings' />

Check the result below:

![Telerik Slider for .NET MAUI Ticks](images/slider-ticks-settings.png)

## Tick Template

Through the `TickTemplate` property you can customize the appearance of the ticks.

* `TickTemplate (DataTemplate)`&mdash;Defines the template of the Slider ticks.

Check below a sample `TickTemplate` example:

**1.** First define the custom DataTemplate:

<snippet id='slider-ticks-ticktemplate-datatemplate' />

**2.** Then apply it to the Slider's `TickTemplate`:

<snippet id='slider-ticks-ticktemplate-xaml' />

![Telerik Slider for .NET MAUI Ticks Template](images/slider-ticks-template.png)

## See Also

- [Backtrack Configuration]({% slug slider-backtrack-configuration%})
- [Labels]({% slug slider-labels%})
- [Ticks Styling]({% slug slider-ticks-styling%})