---
title: Default Dates
page_title: .NET MAUI DatePicker Documentation - Default Dates
description: Define preselected dates in the Telerik UI for .NET MAUI DatePicker and in its spinner.
position: 5
previous_url: /controls/datepicker/datepicker-default-dates
slug: datepicker-default-dates
---

# .NET MAUI DatePicker Default Dates

You can define preselected dates both in the DatePicker (the selected date) and in the spinner (the highlighted date).

## Defining the Current Date Selection

To define the current date selection:

1. Set the `Date` property of the `DateTime?` type. The default value is `null`.

 ```XAML
<telerik:RadDatePicker Date="2020,05,15"
                            SpinnerFormat="yyy-MMM"/>
 ```

1. Add the following namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

## Setting the Highlighted Date

To set the highlighted date:

1. Set the `DefaultHighlightedDate` property of type `DateTime` to define the `System.DateTime`, which will be used to pre-scroll each spinner when the `Date` property is `null`.

 ```XAML
<telerik:RadDateTimePicker Date="{x:Null}"
                                DefaultHighlightedDate="2020,05,15"
                                SpinnerFormat="dd/MMM/yyyy"/>
 ```

1. Add the following namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

## See Also

- [Formatting the Telerik UI for .NET MAUI DatePicker]({%slug datepicker-formatting%})
- [Setting Date Ranges in the .NET MAUI DatePicker]({%slug datepicker-date-range%})
- [.NET MAUI DatePicker Templates]({%slug datepicker-templates%})
- [.NET MAUI DatePicker Selection]({%slug datepicker-selection%})
- [.NET MAUI DatePicker Styling]({%slug datepicker-styling%})
- [.NET MAUI DatePicker Product Page](https://www.telerik.com/maui-ui/datepicker)
