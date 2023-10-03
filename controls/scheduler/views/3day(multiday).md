---
title: Multiday View Definition
page_title: .NET MAUI Day View Documentation - Multiday View 
description: Learn more about the multiday view definition in the Telerik UI for .NET MAUI Scheduler control.
position: 3
slug: scheduler-week-view
---

# Multiday View 

The Telerik UI for .NET MAUI Scheduler control provides the functionality of displaying the data in different views. The control defines four predefined views from which you can choose to navigate through: 

* `DayViewDefinition`
* `WeekViewDefinition`
* `MultidayViewDefinition`
* `MonthViewDefinition`

The Multiday View definition represents a definition of a view that shows multiple days as in day view mode.

![.NET MAUI Scheduler Multiday View](images/)

## Set the Multiday View 

`RadScheduler` has different definitions for each view. It has four types of predefined view definitions. To include the Multiday View definition in the `RadScheduler` control, it have to be defined as follows:

// code snippet here 
<snippet id=''/>

## Properties

* `DayStartTime`&mdash;Defines the time used to indicate the start of the day.
* `DayEndTime`&mdash;Defines the time used to indicate the end of the day.
* `IsCurrentTimeIndicatorVisible`&mdash;Defines the value indicating whether the current time indicator is visible.
* `MajorTickLength`&mdash;Defines the length of the major ticks.
* `MinorTickLenght`&mdash;Defines the length of the minor ticks.
* `MinTimeRulerExtent`&mdash;Defines the minimum size of the time ruler in pixels.
* `VisibleDays`&mdash;Defines the number of visible days in the view.

### Example 

// code snippet here
<snippet id=''/>

![.NET MAUI Scheduler Multiday View Example](images/)


## See Also

- 
- 
- 
- 