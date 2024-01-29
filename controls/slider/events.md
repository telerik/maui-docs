---
title: Events
page_title: .NET MAUI Slider Documentation - Events
description: Learn about the ValueChanging event that the Telerik UI for .NET MAUI Slider control exposes and find out how to use it.
position: 10
slug: slider-events
---

# .NET MAUI Slider Events

The Telerik UI for .NET MAUI Slider component exposes a `ValueChanging` event which is raised when the end user drags the thumb or touches the range track. You can use this event to plug custom logic by changing the `Value` property.

The `ValueChanging` event handler receives two parameters:

* The sender argument, which is of type `object`, but can be cast to the `RadSlider` type.
* A `Telerik.Maui.ValueChangingEventArgs` object, which provides the `Value` property of the Slider.

The following example demonstrates how to use the `ValueChanging` event to prevent dragging the thumb to a smaller value:

**1.** Define the Slider:

```XAML
<telerik:RadSlider Minimum="0"
                   Maximum="100"
                   Value="35"
                   ValueChanging="Slider_ValueChanging" />
```

**2.** Add the event handler:

```C#
private void Slider_ValueChanging(object sender, Telerik.Maui.ValueChangingEventArgs e)
{
    var slider = (RadSlider)sender;
    if (e.Value < 20)
    {
        e.Value = slider.Value;
    }
}
```

## See Also

- [Value Thumb]({%slug slider-value-thumb%})
- [Range Track)({%slug slider-range-track%})
