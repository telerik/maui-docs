---
title: TimeSpan Ranges
page_title: .NET MAUI TimeSpanPicker Documentation | TimeSpan Ranges
description: Check our &quot;TimeSpan Range&quot; documentation article for Telerik TimeSpanPicker for .NET MAUI.
position: 3
slug: timespanpicker-timespan-range
---

## TimeSpan Ranges

The TimeSpanPicker allows you to define a time-span range and choose a time interval within that range through the following properties:

* `MinimumTime`(`TimeSpan`)&mdash;Defines the lowest limit of the available selection range. The default value is `TimeSpan(0, 0, 0, 0, 0)`.

* `MaximumTime`(`TimeSpan`)&mdash;Defines the uppermost limit of the available selection range. The default value is `TimeSpan(30, 23, 59, 59)`.

>important If you set a negative value for `MinimumTime`, the TimeSpanPicker will consider this value to be the minimum `TimeSpan(0, 0, 0, 0, 0)` value.

**Example for Setting Time Ranges**

1. Define the TimeSpanPicker.

 ```XAML
<telerikInput:RadTimeSpanPicker MinimumTime="0:0:00:00"
                                MaximumTime="8:00:00:0"/>
 ```

1. Add the namespace.

 ```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
 ```

## See Also

- [Templates]({%slug timespanpicker-templates%})
- [Styling]({%slug timespanpicker-styling%})
- [Commands]({%slug timespanpicker-commands%})
- [Selection]({%slug timespanpicker-selection%})
