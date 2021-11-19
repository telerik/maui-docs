---
title: Time Steps
page_title: .NET MAUI TimeSpanPicker Documentation | Time Steps
description: Check our &quot;Time Steps&quot; documentation article for Telerik TimeSpanPicker for .NET MAUI.
position: 3
slug: timespanpicker-timespan-steps
---

# Incremental Time Steps

By default, the TimeSpanPicker increments each part of its time values by one step.

You can change the default setup using the following properties:

* `DayStep`(`int`)&mdash;Controls the incremental step of the day value. The default value is `1`.
* `HourStep`(`int`)&mdash;Controls the incremental step of the hour value. The default value is `1`.
* `MinuteStep`(`int`)&mdash;Controls the incremental step of the minute value. The default value is `1`.
* `SecondStep`(`int`)&mdash;Controls the incremental step of the second value. The default value is `1`.

**Example for Setting Time Steps**

1. Define the TimeSpanPicker.

 ```XAML
<telerikInput:RadTimeSpanPicker DayStep="2"
                                HourStep="4"
                                MinuteStep="10"
                                SecondStep="30"/>
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
