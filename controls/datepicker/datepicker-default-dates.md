---
title: Default Dates
page_title: .NET MAUI DatePicker Documentation | Default Dates
description: Check our &quot;Key Features&quot; documentation article for Telerik DatePicker for .NET MAUI.
position: 4
slug: datepicker-default-dates
---

# Default Dates

This article will explain how you can define preselected dates both in the DatePicker - the selected date, and in the spinner - the highlighted date.

## Current Selected Date

Through the `Date` property of type *DateTime?* you can define the current date selection. The default value is null.

### Example 

<snippet id='datepicker-keyfeatures-date-spinnerformat' />
```XAML
<telerikInput:RadDatePicker Date="2020,05,15"
                            SpinnerFormat="yyy-MMM"/>
```

and add the following namespace:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

## Default Highlighted Date

RadDatePicker `DefaultHighlightedDate` of type *DateTime* defines the System.DateTime which will be used to pre-scroll each spinner when `Date` property is set to null.

### Example

```XAML
<telerikInput:RadDateTimePicker Date="{x:Null}"
                                DefaultHighlightedDate="2020,05,15"
                                SpinnerFormat="dd/MMM/yyyy"/>
```

and the namespace needed:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

## See Also

- [Templates]({%slug datepicker-templates%})
- [Styling]({%slug datepicker-styling%})
- [Commands]({%slug datepicker-commands%})
- [Selection]({%slug datepicker-selection%})
