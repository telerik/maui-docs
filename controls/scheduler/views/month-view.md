---
title: Month View
page_title: .NET MAUI Month View Documentation - Month View 
description: Learn more about the month view in the Telerik UI for .NET MAUI Scheduler control.
position: 4
slug: scheduler-month-view
---

# Month View 

The Month View displays appointments in one month and allows users to browse through long-term periods. It is always grouped by week.

## Set the Month View

Add a `MonthViewDefinition` to the `ViewDefinitions` collection of the `RadScheduler` instance.

```XAML
<telerik:RadScheduler x:Name="scheduler">
    <telerik:RadScheduler.ViewDefinitions>
        <telerik:MonthViewDefinition />
    </telerik:RadScheduler.ViewDefinitions>
</telerik:RadScheduler>
```

![](../images/scheduler-monthview.png)

## Properties

* `FirstDayOfWeek`&mdash;Defines the day that is considered the beginning of the week.
* `HeaderTextFormat`&mdash;Defines the format string for the header text. 

## See Also

- [Views]({%slug scheduler-overview %})
- [Day View]({%slug scheduler-day-view%})
- [Multiday View]({%slug scheduler-multiday-view %})
- [Week View]({%slug scheduler-week-view %})