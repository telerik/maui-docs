---
title: Custom Date Formats
page_title: .NET MAUI Scheduler Documentation - Custom Date Formats
description: Learn more about the custom date formats feature in the Telerik UI for .NET MAUI Scheduler control.
position: 11
slug: scheduler-custom-date-formats
---

# .NET MAUI Scheduler Custom Date Formats

The Telerik UI for .NET MAUI Scheduler control provides built-in date formatting support. You can customize each Scheduler view to use custom formats for displaying dates and times on the time ruler and in the headers.

You can use the following date format properties for the different views:

## Multiday Views (Day, Week and MultiDay)

* `HeaderTextFormat`&mdash;Defines the string format of the header text.
* `DayStringFormat`&mdash;Defines the string format of the header days.
* `TimeRulerMajorTickStringFormat`&mdash;Defines the string format of the major ticks.

![Telerik .NET MAUI Scheduler Date Formats Multiday View](images/scheduler-customformats-multiday.png)

## Month View

* `HeaderTextFormat`&mdash;Defines the string format of the header text.
* `DayStringFormat`&mdash;Defines the string format of the header days.
* `WeekDayStringFormat`&mdash;Defines the string format of the week day dates.

![Telerik .NET MAUI Scheduler Date Formats Month View](images/scheduler-customformats-monthview.png)

## Example

Check a quick example on how to apply custom date formats to the Scheduler views:

<snippet id='scheduler-custom-date-formats' />

And here is he result:

![Telerik .NET MAUI Scheduler Custom Date Formats](images/scheduler-customformats-applied-multiday.png)

## See Also

- [Visual Structure]({%slug scheduler-visual-structure %}) 
- [Views]({%slug scheduler-views-overview%})
