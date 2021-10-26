---
title: Date Range
page_title: .NET MAUI Date Picker Documentation | Date Range
description: Check our &quot;Date Range&quot; documentation article for Telerik DatePicker for .NET MAUI.
position: 3
slug: date-picker-date-range
---

# Date Range


Date Picker allows you to define a date range and choose a date in between through the following properties:

* `MinimumDate`(*DateTime*): Defines a date which marks the beginning of the range of the available dates. The default value is *DateTime(2000,1,1)*.

* `MaximumDate` (*DateTime*): Defines a date which marks the end of the range of the available dates to choose from. The default value is *DateTime(2099, 12, 31, 23, 59, 59)*.

### Example

<snippet id='datepicker-keyfeatures-minmaxdate' />
```XAML
<telerikInput:RadDatePicker MinimumDate="2020,1,1"
                            MaximumDate="2020,12,31"
                            DisplayStringFormat="yyy-ddd-MMM"/>
```

Use the following namespace:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

## See Also

- [Templates]({%slug date-picker-templates%})
- [Styling]({%slug date-picker-styling%})
- [Commands]({%slug date-picker-commands%})
- [Selection]({%slug date-picker-selection%})
