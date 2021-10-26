---
title: Default TimeSpan 
page_title: .NET MAUI TimeSpan Picker Documentation | Default TimeSpan
description: Check our &quot;Default TimeSpan&quot; documentation article for Telerik TimeSpan Picker for .NET MAUI.
position: 3
slug: timespan-picker-default-timespan
---

# Default TimeSpan

This article shows the options you can use to set a default time to the RadTimeSpanPicker control.

## Current Selected Time Interval

* `Time`(*TimeSpan?*): Defines the current selection of time interval. The default value is null.

### Example 

```XAML
<telerikInput:RadTimeSpanPicker Time="5:10:30:00"/>
```

And the namespace used:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

## DefaultHighlightedTime Interval

* `DefaultHighlightedTime`(*TimeSpan*) defines the System.TimeSpan which will be used to pre-scroll each spinner when RadTimeSpanPicker.Time property is set to null.

### Example

```XAML
<telerikInput:RadTimeSpanPicker DefaultHighlightedTime="5:10:30:00"
                                            SpinnerFormat="G"
                                            AreSpinnerHeadersVisible="False"/>
```

And the namespace used:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

## See Also

- [Templates]({%slug timespan-picker-templates%})
- [Styling]({%slug timespan-picker-styling%})
- [Commands]({%slug timespan-picker-commands%})
- [Selection]({%slug timespan-picker-selection%})
