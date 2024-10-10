---
title: Using DateOnly
page_title: .NET MAUI Date Picker Documentation - Date Only Support
description: Take advantage of the DateOnly type and make your dates even better when working with the Telerik UI for .NET MAUI DatePicker.
position: 4
slug: datepicker-dateonly
---

# Using DateOnly in the .NET MAUI DatePicker

If your application needs to store or manipulate only the dates without times, you can take advantage of the `DateOnly` struct when working with the DatePicker control.

You can set a `DateOnly` value to the `MinimumDate`, `MaximumDate`, `Date`, and `DefaultHighlightedDate` properties by using the Telerik `DateOnlyToDateTimeConverter `converter. The converter converts `System.DateOnly` to `System.DateTime` and `System.DateTime` to `System.DateOnly`.

Here is the converter definition in XAML:

<snippet id='datepicker-dateonly-to-datetimeconverter' />

The following example demonstrates how to set `DateOnly` in the DatePicker using a converter.

**1.** Define the control and the properties:

<snippet id='datepicker-dateonly-support' />

**2.** Define the converter in the Page's resource:

<snippet id='datepicker-dateonly-to-datetimeconverter' />

**3.** Add the `telerik` namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

 **4.** Add the `ViewModel`:

 <snippet id='datepicker-dateonly-viewmodel' />

## See Also

- [Formatting the Telerik UI for .NET MAUI DatePicker]({%slug datepicker-formatting%})
- [.NET MAUI DatePicker Templates]({%slug datepicker-templates%})
- [.NET MAUI DatePicker Selection]({%slug datepicker-selection%})
- [.NET MAUI DatePicker Styling]({%slug datepicker-styling%})
- [.NET MAUI DatePicker Product Page](https://www.telerik.com/maui-ui/datepicker)
