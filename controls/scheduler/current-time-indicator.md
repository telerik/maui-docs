---
title: Current Time Indicator
page_title: .NET MAUI Scheduler Documentation - Current Time Indicator
description: Learn more about the current time indicator feature in the Telerik UI for .NET MAUI Scheduler control.
position: 10
slug: scheduler-time-indicator
---

# Current Time Indicator 

The Telerik UI for .NET MAUI Scheduler control provides the option to visually mark the current time in the `TimeRuler` and across the Appointments area through the views' `IsCurrentTimeIndicatorVisible` property.

* `IsCurrentTimeIndicatorVisible(type bool)`&mdash;Defines a value that indicates whether the current time indicator is visible across the active view. 

## Disable the CurrentTimeIndicator

Current Time Indicator is enabled by default, you can hide it by setting `IsCurrentTimeIndicatorVisible` to `False`:


To display the current time indicator, you must set the `IsCurrentTimeIndicatorVisible` property of the corresponding view as in the example below:

<snippet id='scheduler-current-time-indicator' />
