---
title: Events
page_title: .NET MAUI RangeSlider Documentation - Events
description: Learn about the events that the Telerik UI for .NET MAUI RangeSlider control exposes and find out how to use them.
position: 9
slug: rangeslider-events
---

# .NET MAUI RangeSlider Events

The Telerik UI for .NET MAUI RangeSlider component exposes a `RangeChanging` event which is raised when the end user drags the start/end thumb or the range track. You can use this event to plug custom logic by changing the `RangeStart` or `RangeEnd` properties.

The `RangeChanging` event handler receives two parameters:

* The sender argument, which is of type `object`, but can be cast to the `RadRangeSlider` type.
* A `RangeChangingEventArgs` object, which provides `RangeStart` and `RangeEnd` properties of the RangeSlider.

The following example demonstrates how to use the `RangeChanging` event to prevent dragging the start/end thumbs in case the range is less than 20:

**1.** Define the RangeSlider:

```XAML
<telerik:RadRangeSlider Minimum="0"
                        Maximum="100"
                        RangeStart="25"
                        RangeEnd="65"
                        RangeChanging="RangeSlider_RangeChanging" />
```

**2.** Add the event handler:

```C#
private void RangeSlider_RangeChanging(object sender, Telerik.Maui.RangeChangingEventArgs e)
{
	var rangeSlider = (RadRangeSlider)sender;
	if((e.RangeEnd - e.RangeStart) < 20)
	{
		e.RangeStart = rangeSlider.RangeStart;
		e.RangeEnd = rangeSlider.RangeEnd;
	}
}
```

## See Also

- [Range Thumb]({%slug rangeslider-range-thumb%})