---
title: Time Range
page_title: .NET MAUI TimePicker Documentation | Time Range
description: Check our &quot;Time Range&quot; documentation article for Telerik TimePicker for .NET MAUI.
position: 2
slug: timepicker-time-range
---

# Time Range

Time Picker allows you to define a time range and choose a time in between through the following properties:

* `MinimumTime`(*TimeSpan*): Defines a time which marks the beginning of the range of the available time values. The default value is `TimeSpan.Zero`.

* `MaximumTime`(*TimeSpan*): Defines a time which marks the end of the range of the available time values to choose from. The default value is `TimeSpan(23, 59, 59)`.

## Example

RadTimePicker definition:

```XAML
<telerikInput:RadTimePicker MinimumTime="8:00:00"
                         MaximumTime="19:00:00"/>
```

Add the namespace:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

## See Also

- [Templates]({%slug timepicker-templates%})
- [Time Format Strings]({%slug timepicker-formatting%})
- [Styling]({%slug timepicker-styling%})
- [Selection]({%slug timepicker-selection%})
- [Commands]({%slug timepicker-commands%})
