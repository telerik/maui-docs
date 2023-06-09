---
title: Day Styling
page_title: .NET MAUI Calendar Documentation - Day Styling
description: Learn how to style the days in a month view of the Telerik .NET MAUI Calendar control.
position: 3
slug: calendar-day-styling
---

# .NET MAUI Calendar Day Styling

The Calendar control for .NET MAUI provides the `DayStyleSelector`(of type `CalendarStyleSelector`) property which specifies the style selector for the days in the month views of the Calendar.

The following example demonstrates how to style the days with the `DayStyleSelector` property:

**1.** Define the Calendar:

<snippet id='calendar-styleselectors-daystyleselector-usage'/>

**2.** The style selectors defined in the page's resources:

<snippet id='calendar-styleselectors-daystyleselector-definition'/>

**3.** Add the `CustomStyleSelector` class that inherits from `CalendarStyleSelector`:

<snippet id='calendar-styleselectors-custom-calendarstyleselector'/>

>For a runnable example demonstrating how to style the days in the Calendar, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **Calendar > Style Selector**.
