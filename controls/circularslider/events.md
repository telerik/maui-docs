---
title: Events
page_title: .NET MAUI CircularSlider Documentation - Events
description: Learn about the ValueChanging event that the Telerik UI for .NET MAUI CircularSlider control exposes and find out how to use it.
position: 11
slug: circularslider-events
---

# .NET MAUI CircularSlider Events

The Telerik UI for .NET MAUI CircularSlider component exposes a `ValueChanging` event which is raised when the end user drags the thumb or touches the range track. You can use this event to plug custom logic by changing the `Value` property.

The `ValueChanging` event handler receives two parameters:

* The sender argument, which is of type `object`, but can be cast to the `RadCircularSlider` type.
* A `Telerik.Maui.ValueChangingEventArgs` object, which provides the `Value` property of the CircularSlider.

The following example demonstrates how to use the `ValueChanging` event to prevent dragging the thumb to a smaller value:

1. Define the CircularSlider:

<snippet id='circularslider-valuechanging-xaml' />

2. Add the event handler:

<snippet id='circularslider-valuechanging-csharp' />

3. Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

## See Also

- [Value Thumb]({%slug circularslider-value-thumb%})
- [Range Track]({%slug circularslider-range-track%})
