---
title: Month Styling
page_title: .NET MAUI Calendar Documentation - Month Styling
description: Learn how to style the months in a year view of the Telerik .NET MAUI Calendar control.
position: 4
slug: calendar-month-styling
---

# .NET MAUI Calendar Month Styling

The Calendar control for .NET MAUI provides the `MonthStyleSelector`(of type `CalendarStyleSelector`) property which specifies the style selector for the months in the year view of the Calendar.

The following example demonstrates how to style the months with the `MonthStyleSelector` property:

**1.** Define the Calendar:

<snippet id='calendar-styleselectors-monthstyleselector-usage'/>

**2.** The style selectors defined in the page's resources:

<snippet id='calendar-styleselectors-monthstyleselector-definition'/>

**3.** Add the `CustomStyleSelector` class that inherits from `CalendarStyleSelector`:

<snippet id='calendar-styleselectors-custom-calendarstyleselector'/>

>For a runnable example demonstrating how to style the months in the Calendar, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **Calendar > Style Selector**.

## See Also

- [Day Styling]({%slug calendar-day-styling%})
- [Decade Styling]({%slug calendar-decade-styling%})
- [Header Styling]({%slug calendar-header-styling%})
- [Year Styling]({%slug calendar-year-styling%})
