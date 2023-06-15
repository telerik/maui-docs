---
title: Year Styling
page_title: .NET MAUI Calendar Documentation - Year Styling
description: Learn how to style the years in a decade view of the Telerik .NET MAUI Calendar control.
position: 5
slug: calendar-year-styling
---

# .NET MAUI Calendar Year Styling

Calendar control for .NET MAUI provides the `YearStyleSelector`(of type `CalendarStyleSelector`) property which specifies the style selector for the years in the decade view of the calendar.

The following example demonstrates how to style the years with the `YearStyleSelector` property:

**1.** Define the Calendar:

<snippet id='calendar-styleselectors-yearstyleselector-usage'/>

**2.** The style selectors defined in the page's resources:

<snippet id='calendar-styleselectors-yearstyleselector-definition'/>

**3.** Add the `CustomStyleSelector` class that inherits from `CalendarStyleSelector`:

<snippet id='calendar-styleselectors-custom-calendarstyleselector'/>

>For a runnable example demonstrating how to style the years in the Calendar, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **Calendar > Style Selector**.

## See Also

- [Day Styling]({%slug calendar-day-styling%})
- [Decade Styling]({%slug calendar-decade-styling%})
- [Header Styling]({%slug calendar-header-styling%}) 
- [Month Styling]({%slug calendar-month-styling%})