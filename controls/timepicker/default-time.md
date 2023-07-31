---
title: Default Time
page_title: .NET MAUI TimePicker Documentation - Default Time
description: Learn more about the options for setting the default time of the Telerik UI for .NET MAUI TimePicker control.
position: 2
previous_url: /controls/timepicker/timepicker-default-time
slug: timepicker-default-time
---

# .NET MAUI TimePicker Default Time

The TimePicker provides options for setting its default time.

## Current Selected Time

To define the currently selected time, use the `Time`(`TimeSpan?`) property, which defines the current time selection. The default value is `null`.

The following example shows how to set the currently selected time.

Define the TimePicker.

```
<telerik:RadTimePicker Time="10:30:00"/>
```

Add the namespace.

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

## Default Highlighted Time

The TimePicker enables you to set its default highlighted time by using the  `DefaultHighlightedTime`(`TimeSpan`) property, which defines the `System.TimeSpan` that will be used to pre-scroll each spinner when the `RadTimePicker.Time` property is set to `null`.

The following example shows how to set the default highlighted time.

Define the TimePicker.

```XAML
<telerik:RadTimePicker DefaultHighlightedTime="11:30:00"
                       SpinnerFormat="t"
                       AreSpinnerHeadersVisible="False"/>
```

Add the namespace.

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```
 

## See Also

- [Templates]({%slug timepicker-templates%})
- [Formatting]({%slug timepicker-formatting%})
- [Styling]({%slug timepicker-styling%})
- [Selection]({%slug timepicker-selection%})
- [Commands]({%slug timepicker-commands%})
