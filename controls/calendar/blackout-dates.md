---
title: Blackout Dates
page_title: .NET MAUI Calendar Documentation - Blackout Dates
description: Discover the blackout dates feature of the Telerik Calendar for .NET MAUI control, and learn how to use them to disable specific dates.
position: 3
slug: calendar-blackout-dates
---

# .NET MAUI Calendar Blackout Dates

The Calendar component for .NET MAUI provides a simple way to disable specific dates. To take advantage of this feature, specify the `BlackoutDates`(`IEnumerable&lt;DateTime&gt;`) collection and the user will not be able to select the defined dates.

## Disabled (Blackout) Dates Example

The following snippets show how to disable certain dates in Calendar control.

**1.** Define the `RadCalendar` control in XAML.

<snippet id='calendar-blackout-dates'/>

**2.** Add a VieWModel with defined blackout dates. 

<snippet id='calendar-blackoutdates-viewmode'/>

> For the complete example with the Calendar Blackout dates, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **Calendar > Features** category.

## See Also

- [Navigation]({%slug calendar-navigation%})
- [Formatting]({%slug calendar-date-formatting%})
- [Selection modes]({%slug calendar-selection%}) 
- [Events]({%slug calendar-events%})
- [Commands]({%slug calendar-commands%})
- [Templates]({%slug calendar-templates-overview%})
- [Styling]({%slug calendar-header-styling%})
