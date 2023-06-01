---
title: Date Porperties
page_title: .NET MAUI Calendar Documentation - Date Porperties
description: Review all properties for setting the min and max date, selected date and display date of the Telerik Calendar for .NET MAUI control.
position: 3
slug: calendar-date-properties
---

# .NET MAUI Calendar Date Properties

This article lists the date properties you could use to configure Calendar control.

## Setting the display date

* `DisplayDate`(`DataTemplate`)&mdash;Defines the template of the header that will be visualized in the drop down list.

## Constraining visible dates

Restrict the visible/selectable dates in Calendar by utilizing `MinDate` and `MaxDate` properties.

* `MinDate`(`DateTime`)&mdash;Specifies the earliest date that the calendar can display.
* `MaxDate`(`DateTime`)&mdash;Specifies the latest date that the calendar can display.

By applying `MinDate` and `MaxDate` you prevents navigating the Calendar to a date outside of the defined date range.

<snippet id='calendar-date-properties'/>

> For the Calendar Date Properties example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to Calendar -> Features category.

>tip If dates are outside of the MinDate-MaxDate range are in the currently visible view, they look disabled.

## Day names visibility

By default the day names (in Month view) are visible. You can easily hide the day names by setting the `AreDayNamesVisible`(`bool`) property to `False`.

<snippet id='calendar-daynames-visibility'/>

> For the Calendar DayNames Visibility example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to Calendar -> Features category.

## Leading and trailing days visibility

By defaylt the leading and trailing days in the month, year, century and decade are visible. You can hide them by setting the `IsOutOfScopeVisible`(`bool`) property to `False`.

<snippet id='calendar-outofscope-visibility'/>

> For the Calendar OutOfscope Visibility example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to Calendar -> Features category.

## Setting the first day of week

 * `FirstDayOfWeek`(enum of type ` System.DayOfWeek?`)&mdash;Specifies the day that is considered the beginning of the week.

<snippet id='calendar-culture'/>

## Selecting a date

`SelectedDate`(`DateTime?`) property holds the currently selected date, `null` means that no date is selected. For more details on the selection functionality, refer to [Selection]({%slug calendar-selection%}) topic.

## Blackout dates

Calendar allows you to specify a collection of dates that cannot be selected by the user. This list is called `BlackoutDates`(`IEnumerable&lt;DateTime&gt;`).

<snippet id='calendar-blackout-dates'/>

> For the Calendar Blackout dates example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to Calendar -> Features category.

## See Also

- [Navigation]({%slug calendar-navigation%})
- [Formatting]({%slug calendar-date-formatting%})
- [Selection modes]({%slug calendar-selection%}) 
- [Events]({%slug calendar-events%})
- [Commands]({%slug calendar-commands%})
- [Templates]({%slug calendar-templates-overview%})
- [Styling]({%slug calendar-header-styling%})