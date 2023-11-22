---
title: Visible Range
page_title: .NET MAUI Scheduler Documentation - Visible Range
description: Learn more about the visible range of the Telerik UI for .NET MAUI Scheduler control.
position: 10
slug: scheduler-visible-range
---

# .NET MAUI Scheduler Visible Range

The .NET MAUI Scheduler exposes `VisibleRange` property which you can use to get the currently displayed days inside the active view.

* `VisibleRange`(`IDateRange`)&mdash;Gets the period/dates range that is currently visible inside the Scheduler view. `VisibleRange` provides the following properties:
    * `Start`(`DateTime`)
    * `End`(`DateTime`)

The visible range depends on the view - for some views such as Month View it is predefined and for other views such as MultiDay View you can define it through the `VisibleDays` property.

You can use `VisibleRange` to get notified when the view is changed as well as when the user navigates through the dates of the active view. For that purpose subscribe to `PropertyChanged` of the Scheduler and look for `VisibleRange` changes:

```XAML
<telerik:RadScheduler x:Name="scheduler"
                      PropertyChanged="Scheduler_PropertyChanged">
    <telerik:RadScheduler.ViewDefinitions>
        <telerik:WeekViewDefinition />
        <telerik:WeekViewDefinition IsWeekendVisible="False" Title="Work Week" />
        <telerik:MultidayViewDefinition VisibleDays="3" Title="3 Day" />
        <telerik:DayViewDefinition />
        <telerik:MonthViewDefinition />
    </telerik:RadScheduler.ViewDefinitions>
</telerik:RadScheduler>
```

And here is the event handler:

```C#
private void Scheduler_PropertyChanged(object sender, System.ComponentModel.PropertyChangedEventArgs e)
{
	if(e.PropertyName == "VisibleRange")
	{
		var startDate = (sender as RadScheduler).VisibleRange.Start;
		var endDate = (sender as RadScheduler).VisibleRange.End;
	}
}
```

## See Also

- [Views]({% slug scheduler-views-overview %})
- [Month View]({%slug scheduler-month-view%})
- [MultiDay View]({%slug scheduler-multiday-view%})