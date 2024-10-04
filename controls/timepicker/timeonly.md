---
title: TimeOnly Support
page_title: .NET MAUI TimePicker Documentation - TimeOnly Support
description: Set date only type in the Telerik UI for .NET MAUI TimePicker.
position: 4
slug: timepicker-timeonly
---

# TimeOnly Support in .NET MAUI TimePicker

The TimePicker has a support for `TimeOnly`. You can set a `TimeOnly` value to the `MinimumTime`, `MaximumTime`, `Time` and `DefaultHighlightedTime` properties by using the Telerik `TimeOnlyToTimeSpanConverter `converter. The converter converts `System.TimeOnly` to `System.TimeSpan` and converts back `System.TimeSpan` to `System.TimeOnly`.

Here is the converter definition in XAML:

<snippet id='timepicker-timeonly-to-timespanconverter' />

The following example demonstrates how to set `TimeOnly` in the TimePicker using a converter.

**1.** Define the TimePicker control and the time properties:

<snippet id='timepicker-timeonly-support' />

**2.** Define the converter in the Page's resource:

<snippet id='timepicker-timeonly-to-timespanconverter' />

**3.** Add the `telerik` namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

 **4.** Add the `ViewModel`:

 <snippet id='timepicker-timeonly-viewmodell' />

## See Also

- [Templates]({%slug timepicker-templates%})
- [Time Format Strings]({%slug timepicker-formatting%})
- [Styling]({%slug timepicker-styling%})
- [Selection]({%slug timepicker-selection%})
- [Commands]({%slug timepicker-commands%})
