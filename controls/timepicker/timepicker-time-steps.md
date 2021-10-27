---
title: Time Steps
page_title: .NET MAUI TimePicker Documentation | Time Steps
description: Check our &quot;Time Steps&quot; documentation article for Telerik TimePicker for .NET MAUI.
position: 2
slug: timepicker-time-steps
---

# Time Steps

By default the TimePicker increments each part of its time values by one step. You can change the default setup using the following properties:

* `HourStep`(*int*): Controls the incremental step of the hour value. Default value is `1`.
* `MinuteStep`(*int*): Controls the incremental step of the minute value. Default value is `1`. 
* `SecondStep`(*int*): Controls the incremental step of the second value. Default value is `1`.

## Example

RadTimePicker definition:

```XAML
<telerikInput:RadTimePicker HourStep="2" 
                         MinuteStep="10" 
                         SecondStep="30"/>
```

Add the namespace:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

## See Also

- [Templates]({%slug timepicker-templates%})
- [Time Format Strings]({%slug timepicker-formatting%})
- [Styling]({%slug timepicker-styling%})
- [Selection]({%slug timepicker-selection%})
- [Commands]({%slug timepicker-commands%})
