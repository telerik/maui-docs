---
title: Time Ranges
page_title: .NET MAUI TimePicker Documentation - Time Ranges
description: Check our &quot;Time Range&quot; documentation article for Telerik TimePicker for .NET MAUI.
position: 2
previous_url: /controls/timepicker/timepicker-time-range
slug: timepicker-time-range
---

# Time Ranges

The TimePicker allows you to define a time range and choose a time within that range through the following properties:

* `MinimumTime`(`TimeSpan`)&mdash;Defines a time which marks the beginning of the range of the available time values. The default value is `TimeSpan.Zero`.

* `MaximumTime`(`TimeSpan`)&mdash;Defines a time which marks the end of the range of the available time values to choose from. The default value is `TimeSpan(23, 59, 59)`.

The following example shows how to set the time ranges.

1. Define the TimePicker:

 ```XAML
<telerik:RadTimePicker MinimumTime="8:00:00"
                         MaximumTime="19:00:00"/>
 ```

1. Add the namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

## See Also

- [Templates]({%slug timepicker-templates%})
- [Time Format Strings]({%slug timepicker-formatting%})
- [Styling]({%slug timepicker-styling%})
- [Selection]({%slug timepicker-selection%})
- [Commands]({%slug timepicker-commands%})
