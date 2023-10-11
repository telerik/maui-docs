---
title: Day View
page_title: .NET MAUI Day View Documentation - Day View 
description: Learn more about the day view definition in the Telerik UI for .NET MAUI Scheduler control.
position: 1
slug: scheduler-day-view
---

# Day View 

The Day View represents a view that shows a single day.

## Set the Day View 

Add a `DayViewDefinition` to the `ViewDefinitions` collection of the `RadScheduler` instance.

```XAML
<telerik:RadScheduler AutomationId="scheduler">
    <telerik:RadScheduler.ViewDefinitions>
        <telerik:DayViewDefinition />
    </telerik:RadScheduler.ViewDefinitions>
</telerik:RadScheduler>
```

![](../images/scheduler-dayview.png)

## Properties

* `DayStartTime`&mdash;Defines the time used to indicate the start of the day.
* `DayEndTime`&mdash;Defines the time used to indicate the end of the day.
* `IsCurrentTimeIndicatorVisible`&mdash;Defines the value indicating whether the current time indicator is visible. For more details on this go to [Current Time Indicator]({%slug scheduler-time-indicator %}) topic.
* `MajorTickLength`&mdash;Defines the length of the major ticks.
* `MinorTickLength`&mdash;Defines the length of the minor ticks.
* `MinTimeRulerExtent`&mdash;Defines the minimum size of the time ruler in pixels.
* `MaxTimeRulerExtent`&mdash;Defines the maximum size of the time ruler in pixels.

## See Also

- [Views]({%slug scheduler-overview %})
- [Multiday View]({%slug scheduler-multiday-view %})
- [Week View]({%slug scheduler-week-view %})