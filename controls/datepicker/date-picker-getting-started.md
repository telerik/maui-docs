---
title: Getting Started
page_title: Getting Started with .NET MAUI Date Picker Control
description: Check our &quot;Getting Started&quot; documentation article for Telerik DatePicker for .NET MAUI.
position: 1
slug: date-picker-getting-started
---

# Getting Started

This guide demonstrates how to add Telerik UI for .NET MAUI DatePicker control to your application.

At the end, you will be able to achieve the following result:

![RadDatePicker](images/datepicker_getting_started.png)

## Prerequisites

Before adding the DatePicker, first you need to [setup your .NET MAUI app]({%slug maui-getting-started %}#setup-your-net-maui-app), and [download]({% slug maui-getting-started %}#download-telerik-ui-for-net-maui) and [install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#install-telerik-ui-for-net-maui).

## Define RadDatePicker control

<snippet id='datepicker-getting-started-xaml' />
<snippet id='datepicker-getting-started-csharp' />
```XAML
<telerikInput:RadDatePicker x:Name="datePicker" />
```

In addition to this, you need to add the following namespace:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```
```C#
using Telerik.XamarinForms.Input;
```

## See Also

- [Formatting]({%slug date-picker-formatting%})
- [Date Range]({%slug date-picker-date-range%})
- [Templates]({%slug date-picker-templates%})
- [Selection]({%slug date-picker-selection%})
- [Styling]({%slug date-picker-styling%})
