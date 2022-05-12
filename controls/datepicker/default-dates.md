---
title: Default Dates
page_title: .NET MAUI DatePicker Documentation | Default Dates
description: "Define preselected dates in the Telerik DatePicker for .NET MAUI and in the spinner."
position: 4
previous_url: /controls/datepicker/datepicker-default-dates
slug: datepicker-default-dates
---

# Default Dates

You can define preselected dates both in the DatePicker (the selected date) and in the spinner (the highlighted date).

## Defining the Current Date Selection

Through the `Date` property of the `DateTime?` type you can define the current date selection. The default value is `null`.

```XAML
<telerik:RadDatePicker Date="2020,05,15"
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

- [Templates]({%slug datepicker-templates%})
- [Styling]({%slug datepicker-styling%})
- [Commands]({%slug datepicker-commands%})
- [Selection]({%slug datepicker-selection%})
