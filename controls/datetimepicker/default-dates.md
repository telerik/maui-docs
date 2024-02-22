---
title: Default Dates
page_title: .NET MAUI DateTimePicker Documentation - Default Dates
description: Define preselected dates in the Telerik DateTimePicker for .NET MAUI and in the spinner.
position: 4
slug: datetimepicker-default-dates
---

# .NET MAUI DateTimePicker Default Dates

You can define preselected dates both in the DateTimePicker (the selected date) and in the spinner (the highlighted date).

## Defining the Current Date Selection

Through the `Date` property of the `DateTime?` type you can define the current date selection. The default value is `null`.

```XAML
<telerik:RadDateTimePicker Date="2020,05,15"
                                SpinnerFormat="yyy-MMM"/>
```

Add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

## Setting the Highlighted Date

The `DefaultHighlightedDate` property of type `DateTime` defines the `System.DateTime`, which will be used to pre-scroll each spinner when the `Date` property is set to `null`.

```XAML
<telerik:RadDateTimePicker Date="{x:Null}"
                                DefaultHighlightedDate="2020,05,15"
                                SpinnerFormat="dd/MMM/yyyy"/>
```

Add the following namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

## See Also

- [Templates]({%slug datetimepicker-templates%})
- [Styling]({%slug datetimepicker-styling%})
- [Commands]({%slug datetimepicker-commands%})
- [Selection]({%slug datetimepicker-selection%})
