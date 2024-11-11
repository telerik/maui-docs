---
title: Using TimeOnly
page_title: .NET MAUI TimeSpanPicker Documentation - TimeOnly Support
description: Take advantage of the TimeOnly type and make your dates even better when working with the Telerik UI for .NET MAUI TimeSpanPicker.
position: 4
slug: timespanpicker-timeonly
---

# Using TimeOnly in the .NET MAUI TimeSpanPicker

If your application needs to store or manipulate only the time without the date portion, you can take advantage of the `TimeOnly` struct when working with the TimeSpanPicker control.

You can set a `TimeOnly` value to the `MinimumTime`, `MaximumTime`, `Time`, and `DefaultHighlightedTime` properties by using the Telerik `TimeOnlyToTimeSpanConverter `converter. The converter converts `System.TimeOnly` to `System.TimeSpan` and `System.TimeSpan` to `System.TimeOnly`.

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

> For the TimeSpanPicker TimeOnly example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to the **TimeSpanPicker > TimeOnly** category.

## See Also

- [Templates]({%slug timespanpicker-templates%})
- [Styling]({%slug timespanpicker-styling%})
- [Commands]({%slug timespanpicker-commands%})
- [Selection]({%slug timespanpicker-selection%})
