---
title: Blackout Dates
page_title: .NET MAUI Calendar Documentation - Blackout Dates
description: Review how to apply blackout dates of the Telerik Calendar for .NET MAUI control.
position: 3
slug: calendar-blackout-dates
---

# Blackout Dates in .NET MAUI Calendar control

Calendar provides an easier way to disable dates. All you need is to specify a collection of dates that cannot be selected by the user. This collections is the `BlackoutDates`(`IEnumerable&lt;DateTime&gt;`).

## Disable certain dates

The purpose of the following tutorial is to show how to disable certain dates in Calendar control.

The XAML definition of the RadCalendar control:

<snippet id='calendar-blackout-dates'/>

And a sample VieWModel with blackout dates: 

<snippet id='calendar-blackoutdates-viewmode'/>

> For the Calendar Blackout dates example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to Calendar -> Features category.

## See Also

- [Navigation]({%slug calendar-navigation%})
- [Formatting]({%slug calendar-date-formatting%})
- [Selection modes]({%slug calendar-selection%}) 
- [Events]({%slug calendar-events%})
- [Commands]({%slug calendar-commands%})
- [Templates]({%slug calendar-templates-overview%})
- [Styling]({%slug calendar-header-styling%})