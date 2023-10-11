---
title: Week View
page_title: .NET MAUI Day View Documentation - Week View 
description: Learn more about the week view definition in the Telerik UI for .NET MAUI Scheduler control.
position: 2
slug: scheduler-week-view
---

# Week View 

The Week View represents a view that shows all seven week days as in a day view.

## Set the Week View

Add a `WeekViewDefinition` to the `ViewDefinitions` collection of the `RadScheduler` instance.

```XAML
<telerik:RadScheduler AutomationId="scheduler">
    <telerik:RadScheduler.ViewDefinitions>
        <telerik:WeekViewDefinition />
    </telerik:RadScheduler.ViewDefinitions>
</telerik:RadScheduler>
```

![](../images/scheduler-weekview.png)

## Properties

* `DayStartTime`&mdash;Defines the time used to indicate the start of the day.
* `DayEndTime`&mdash;Defines the time used to indicate the end of the day.
* `IsCurrentTimeIndicatorVisible`&mdash;Defines the value indicating whether the current time indicator is visible.
* `MajorTickLength`&mdash;Defines the length of the major ticks.
* `MinorTickLength`&mdash;Defines the length of the minor ticks.
* `MinTimeRulerExtent`&mdash;Defines the minimum size of the time ruler in pixels.

## See Also

- [Views]({%slug scheduler-overview %})
- [Day View]({%slug scheduler-day-view})
- [Multiday View]({%slug scheduler-week-view %})
- [Month View]({%slug scheduler-month-view %})
