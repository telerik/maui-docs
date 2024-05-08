---
title: TimeSpan Ranges
page_title: .NET MAUI TimeSpanPicker Documentation - TimeSpan Ranges
description: Learn more about the time span range functionality in the Telerik UI for .NET MAUI TimePicker control.
position: 3
previous_url: /controls/timespanpicker/timespanpicker-timespan-range
slug: timespanpicker-timespan-range
---

# Time Span Ranges in .NET MAUI TimeSpanPicker

The TimeSpanPicker allows you to define a time-span range and choose a time interval within that range through the following properties:

* `MinimumTime`(`TimeSpan`)&mdash;Defines the lowest limit of the available selection range. The default value is `TimeSpan(0, 0, 0, 0, 0)`.

* `MaximumTime`(`TimeSpan`)&mdash;Defines the uppermost limit of the available selection range. The default value is `TimeSpan(30, 23, 59, 59)`.

>important If you set a negative value for `MinimumTime`, the TimeSpanPicker will consider this value to be the minimum `TimeSpan(0, 0, 0, 0, 0)` value.

The following example shows how to set the time ranges.

Define the TimeSpanPicker:

```XAML
<telerik:RadTimeSpanPicker MinimumTime="0:0:00:00"
                                MaximumTime="8:00:00:0"/>
```

Add the namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

## See Also

- [Templates]({%slug timespanpicker-templates%})
- [Styling]({%slug timespanpicker-styling%})
- [Commands]({%slug timespanpicker-commands%})
- [Selection]({%slug timespanpicker-selection%})
