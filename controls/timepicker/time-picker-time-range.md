---
title: Time Range
page_title: .NET MAUI Time Picker Documentation | Time Range
description: Check our &quot;Time Range&quot; documentation article for Telerik TimePicker for .NET MAUI.
position: 2
slug: time-picker-time-range
---

# Time Range

Time Picker allows you to define a time range and choose a time in between through the following properties:

* **MinimumTime**(*TimeSpan*): Defines a time which marks the beginning of the range of the available time values. The default value is `TimeSpan.Zero`.

* **MaximumTime**(*TimeSpan*): Defines a time which marks the end of the range of the available time values to choose from. The default value is `TimeSpan(23, 59, 59)`.

## Example

1. RadTimePicker definition:

 ```XAML
 <telerikInput:RadTimePicker MinimumTime="8:00:00"
                             MaximumTime="19:00:00"/>
 ```

1. Add the namespace:

 ```XAML
 xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
 ```

## See Also

- [Templates]({%slug time-picker-templates%})
- [Time Format Strings]({%slug time-picker-formatting%})
- [Styling]({%slug time-picker-styling%})
- [Selection]({%slug time-picker-selection%})
- [Commands]({%slug time-picker-commands%})
