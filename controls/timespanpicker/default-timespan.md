---
title: Default TimeSpan
page_title: .NET MAUI TimeSpanPicker Documentation | Default TimeSpan
description: Check our &quot;Default TimeSpan&quot; documentation article for Telerik TimeSpanPicker for .NET MAUI.
position: 3
previous_url: /controls/timespanpicker/timespanpicker-default-timespan
slug: timespanpicker-default-timespan
---

# Default TimeSpan

The TimeSpanPicker provides options for setting its default time interval.

## Current Selected Time Interval

To define the currently selected time, use the `Time`(`TimeSpan?`) property, which defines the current time interval selection. The default value is `null`.

The following example shows how to set the currently selected time interval.

Define the TimeSpanPicker.

```XAML
<telerikInput:RadTimeSpanPicker Time="5:10:30:00"/>
```

Add the namespace.

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```



## DefaultHighlightedTime Interval

The TimeSpanPicker enables you to set its default highlighted time interval by using the  `DefaultHighlightedTime`(`TimeSpan`) property, which defines the `System.TimeSpan` that will be used to pre-scroll each spinner when the `RadTimeSpanPicker.Time` property is set to `null`.

The following example shows how to set the default highlighted time interval.

Define the TimeSpanPicker.

```XAML
<telerikInput:RadTimeSpanPicker DefaultHighlightedTime="5:10:30:00"
                                            SpinnerFormat="G"
                                            AreSpinnerHeadersVisible="False"/>
```

Add the namespace.

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```



## See Also

- [Templates]({%slug timespanpicker-templates%})
- [Styling]({%slug timespanpicker-styling%})
- [Commands]({%slug timespanpicker-commands%})
- [Selection]({%slug timespanpicker-selection%})
