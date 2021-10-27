---
title: Default Time
page_title: .NET MAUI TimePicker Documentation | Default Time
description: Check our &quot;Default Time&quot; documentation article for Telerik TimePicker for .NET MAUI.
position: 2
slug: timepicker-default-time
---

# Default Time

This article shows the options you can use to set a default time to the RadTimePicker control.

## Current Selected Time

* `Time`(*TimeSpan?*): Defines the current time selection. The default value is null.

### Example 

```
<telerikInput:RadTimePicker Time="10:30:00"/>
```

And the namespace:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

## DefaultHighlightedTime

* `DefaultHighlightedTime`(*TimeSpan*) defines the System.TimeSpan which will be used to pre-scroll each spinner when RadTimePicker.Time property is set to null.

### Example

```XAML
<telerikInput:RadTimePicker DefaultHighlightedTime="11:30:00"
                                        SpinnerFormat="t"
                                        AreSpinnerHeadersVisible="False"/>
```

And the namespace:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

## See Also

- [Templates]({%slug timepicker-templates%})
- [Formatting]({%slug timepicker-formatting%})
- [Styling]({%slug timepicker-styling%})
- [Selection]({%slug timepicker-selection%})
- [Commands]({%slug timepicker-commands%})
