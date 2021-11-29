---
title: Date Ranges
page_title: .NET MAUI Date Picker Documentation | Date Ranges
description: "Set and control date ranges in the Telerik DatePicker for .NET MAUI."
position: 3
slug: datepicker-date-range
---

# Date Ranges

The DatePicker allows you to define a date range and choose a date within that range.

To implement date ranges, use the following DatePicker properties:

* `MinimumDate`(`DateTime`)&mdash;Defines a date, which marks the beginning of the range of the available dates. The default value is `DateTime(2000,1,1)`.

* `MaximumDate`(`DateTime`)&mdash;Defines a date, which marks the end of the range of the available dates to choose from. The default value is `DateTime(2099, 12, 31, 23, 59, 59)`.

The following example demonstrates how to set date ranges in the DatePicker.

1. Define the control and the date ranges.

 <snippet id='datepicker-keyfeatures-minmaxdate' />
 ```XAML
<telerikInput:RadDatePicker MinimumDate="2020,1,1"
                            MaximumDate="2020,12,31"
                            DisplayStringFormat="yyy-ddd-MMM"/>
 ```

1. Add the following namespace:

 ```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
 ```

## See Also

- [Templates]({%slug datepicker-templates%})
- [Styling]({%slug datepicker-styling%})
- [Commands]({%slug datepicker-commands%})
- [Selection]({%slug datepicker-selection%})
