---
title: Month View
page_title: .NET MAUI Month View Documentation - Month View 
description: Learn more about the month view in the Telerik UI for .NET MAUI Scheduler control.
position: 4
slug: scheduler-month-view
---

# Month View 

The Month View represents a view that shows 42 days in month view mode.

## Set the Week View

Add a `WeekViewDefinition` to the `ViewDefinitions` collection of the `RadScheduler` instance.

```XAML
<telerik:RadScheduler AutomationId="scheduler">
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
- [Day View]({%slug scheduler-day-view})
- [Multiday View]({%slug scheduler-week-view %})
- [Week View]({%slug scheduler-week-view %})