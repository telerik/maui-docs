---
title: TimeSpan Range
page_title: .NET MAUI TimeSpanPicker Documentation | TimeSpan Range
description: Check our &quot;TimeSpan Range&quot; documentation article for Telerik TimeSpanPicker for .NET MAUI.
position: 3
slug: timespanpicker-timespan-range
---

## TimeSpan Range 

TimeSpanPicker allows you to define a timespan range and choose a time interval in between through the following properties:

* `MinimumTime`(*TimeSpan*): Defines the lowest limit of the available selection range. The default value is `TimeSpan(0, 0, 0, 0, 0)`.

* `MaximumTime`(*TimeSpan*): Defines the upper limit of the available selection range. The default value is `TimeSpan(30, 23, 59, 59)`.

>important If negaive value is set for MinimumTime, the TimeSpan Picker will coerce this value to minimum value - `TimeSpan(0, 0, 0, 0, 0)`.

### Example

```XAML
<telerikInput:RadTimeSpanPicker MinimumTime="0:0:00:00"
                                MaximumTime="8:00:00:0"/>
```

And the namespace:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

## See Also

- [Templates]({%slug timespanpicker-templates%})
- [Styling]({%slug timespanpicker-styling%})
- [Commands]({%slug timespanpicker-commands%})
- [Selection]({%slug timespanpicker-selection%})
