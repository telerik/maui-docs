---
title: Time Steps
page_title: .NET MAUI TimeSpan Picker Documentation | Time Steps
description: Check our &quot;Time Steps&quot; documentation article for Telerik TimeSpan Picker for .NET MAUI.
position: 3
slug: timespan-picker-timespan-steps
---

# Incremental Time Steps

By defaul the TimeSpan Picker increments each part of its time values by one step. You can change the default setup using the following properties:

* `DayStep`(*int*): Controls the incremental step of the day value. Default value is 1.
* `HourStep`(*int*): Controls the incremental step of the hour value. Default value is 1.
* `MinuteStep`(*int*): Controls the incremental step of the minute value. Default value is 1. 
* `SecondStep`(*int*): Controls the incremental step of the second value. Default value is 1.

### Example 

```XAML
<telerikInput:RadTimeSpanPicker DayStep="2"
                                HourStep="4" 
                                MinuteStep="10" 
                                SecondStep="30"/>
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
