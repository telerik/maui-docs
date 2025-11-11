---
title: Multiday View
page_title: .NET MAUI Day View Documentation - Multiday View 
description: Learn more about the multiday view definition in the Telerik UI for .NET MAUI Scheduler control.
position: 3
slug: scheduler-multiday-view
---

# Multiday View 

The MultiDay View represent a view that shows appointments of a defined number of days starting from `CurrentDate`. The Multiday View provides the same properties as the Day View with the only difference that the displayed period is not just a single day. You can define the number of days displayed in MultiDay View through `VisibleDays` property.

## Set the Multiday View

Add a `MultidayViewDefinition` to the `ViewDefinitions` collection of the `RadScheduler` instance with `VisibleDays` and `Title` applied.

```XAML
<telerik:RadScheduler x:Name="scheduler">
    <telerik:RadScheduler.ViewDefinitions>
       <telerik:MultidayViewDefinition VisibleDays="3" Title="3 Days" />
    </telerik:RadScheduler.ViewDefinitions>
</telerik:RadScheduler>
```

![.NET MAUI Scheduler MultiDay View](../images/scheduler-multiday.png)


## Properties

* `DayStartTime`&mdash;Defines the time used to indicate the start of the day.
* `DayEndTime`&mdash;Defines the time used to indicate the end of the day.
* `IsCurrentTimeIndicatorVisible`&mdash;Defines the value indicating whether the current time indicator is visible.
* `MajorTickLength`&mdash;Defines the length of the major ticks.
* `MinorTickLength`&mdash;Defines the length of the minor ticks.
* `MinTimeRulerExtent`&mdash;Defines the minimum size of the time ruler in pixels.
* `MaxTimeRulerExtent`&mdash;Defines the maximum size of the time ruler in pixels.
* `TimeRulerWidth`&mdash;Defines the width of the time ruler in pixels.
* `VisibleDays`&mdash;Defines the number of visible days in the view.

## See Also

- [Views]({%slug scheduler-overview %})
- [Day View]({%slug scheduler-day-view%})
- [Week View]({%slug scheduler-week-view %})
- [Month View]({%slug scheduler-month-view %})
- [Custom Date Formats]({%slug scheduler-custom-date-formats%})
