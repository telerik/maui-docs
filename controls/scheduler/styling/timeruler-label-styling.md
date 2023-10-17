---
title: TimeRuler Labels Styling
page_title: .NET MAUI Scheduler Documentation - TimeRuler Labels Styling
description: Review the styling options that the Telerik UI for .NET MAUI Scheduler control provides for the labels on the time ruler for day, week and multiday views.
position: 5
slug: scheduler-timeruler-labels-styling
---

# .NET MAUI Scheduler TimeRuler Labels Styling

The Scheduler for .NET MAUI provides style property for the labels displayed on the major tick in the time ruler of the day views (Day, Week and MultiDay views).

Through the `TimeRulerLabelStyle` property of the corresponding `ViewDefinition` (Day, Week or MultiDay) you can apply style to the Label controls shown on the major ticks in the time ruler.

Here is a quick example on how `TimeRulerLabelStyle` property can be used:

**1.** Define the Scheduler:

<snippet id='scheduler-timerulerlabelsstyling-definition'/>

**2.** Add the custom styles to the page's resources:

<snippet id='scheduler-timerulerlabels-style'/>

Check the result below:

![Telerik .NET MAUI Scheduler TimeRuler Labels Styling](images/scheduler-timeruler-labels-styling.png)

## See Also

- [Time Ruler]({%slug scheduler-time-ruler%})
- [Views]({%slug scheduler-views-overview %})
- [Lines Styling]({%slug scheduler-lines-styling %})