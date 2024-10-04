---
title: TimeOnly Support
page_title: .NET MAUI TimeSpanPicker Documentation - TimeOnly Support
description: Set date only type in the Telerik UI for .NET MAUI TimeSpanPicker.
position: 4
slug: timespanpicker-timeonly
---

# TimeOnly Support in .NET MAUI TimeSpanPicker

The TimePicker has a support for `TimeOnly`. Set a `TimeOnly` value to the `MinimumTime`, `MaximumTime`, `Time` and `DefaultHighlightedTime` properties by using the Telerik `TimeOnlyToTimeSpanConverter `converter. The converter converts `System.TimeOnly` to `System.TimeSpan` and converts back `System.TimeSpan` to `System.TimeOnly`.

Here is the converter definition in XAML:

<snippet id='timepicker-timeonly-to-timespanconverter' />

The following example demonstrates how to set `TimeOnly` in the TimeSpanPicker using a converter.

**1.** Define the TimeSpanPicker control and the time properties:

<snippet id='timespanpicker-timeonly-support' />

**2.** Define the converter in the Page's resource:

<snippet id='timepicker-timeonly-to-timespanconverter' />

**3.** Add the `telerik` namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

 **4.** Add the `ViewModel`:

 <snippet id='timepicker-timeonly-viewmodell' />

## See Also

- [Templates]({%slug timespanpicker-templates%})
- [Styling]({%slug timespanpicker-styling%})
- [Commands]({%slug timespanpicker-commands%})
- [Selection]({%slug timespanpicker-selection%})
