---
title: Date Ranges
page_title: .NET MAUI DateTime Picker Documentation | Date Ranges
description: "Set and control date ranges in the Telerik DatePicker for .NET MAUI."
position: 3
slug: datetimepicker-date-range
---

# Date Ranges

The DateTimePicker allows you to define a date range and choose a date within that range.

To implement date ranges, use the following DatePicker properties:

* `MinimumDate`(`DateTime`)&mdash;Defines a date, which marks the beginning of the range of the available dates. The default value is `DateTime(2000,1,1)`.

* `MaximumDate`(`DateTime`)&mdash;Defines a date, which marks the end of the range of the available dates to choose from. The default value is `DateTime(2099, 12, 31, 23, 59, 59)`.

The following example demonstrates how to set date ranges in the DatePicker.

Define the control and the date ranges.


```XAML
<telerik:RadDateTimePicker MinimumDate="2020,1,1"
                            MaximumDate="2020,12,31"
                            DisplayStringFormat="yyy-ddd-MMM"/>
```

Add the following namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

## Setting the Time steps

By default, the time component of the DateTimePicker increments or decrements each part of its time values by one step. You can change the default setup using the following properties:

* `HourStep`(`int`)&mdash;Controls the incremental step of the hour value. Default value is 1.

* `MinuteStep`(`int`)&mdash;Controls the incremental step of the minute value. Default value is 1.

* `SecondStep`(`int`)&mdash;Controls the incremental step of the second value. Default value is 1.

## See Also

- [Templates]({%slug datetimepicker-templates%})
- [Styling]({%slug datetimepicker-styling%})
- [Commands]({%slug datetimepicker-commands%})
- [Selection]({%slug datetimepicker-selection%})
