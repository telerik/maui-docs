---
title: Date Properties
page_title: .NET MAUI Calendar Documentation - Date Properties
description: Review all properties for setting the min and max date, selected date, and display date of the Telerik Calendar for .NET MAUI control.
position: 3
slug: calendar-date-properties
---

# .NET MAUI Calendar Date Properties

The .NET MAUI Calendar provides various date properties that allow you to configure the control by setting the display date, restricting the selectable dates, disabling the day names, and more.

## Setting the Display Date

To set the currently displayed date, use the `DisplayDate` property.

* `DisplayDate`(`DataTemplate`)&mdash;Defines the template of the header that will be visualized in the drop down list.

## Constraining Visible Dates and Selection

To limit the visible dates in the Calendar that the user can select, utilize the `MinDate` and `MaxDate` properties. This allows you to prevent the user from navigating the Calendar to a date outside of the defined date range.

As a result, if the currently selected view contains any dates that are outside of the defined `MinDate`-`MaxDate` range, they look disabled.

* `MinDate`(`DateTime`)&mdash;Specifies the earliest date that the Calendar can display.
* `MaxDate`(`DateTime`)&mdash;Specifies the latest date that the Calendar can display.

<snippet id='calendar-date-properties'/>

> For a runnable example with the Calendar Date Properties, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **Calendar > Features** category.

## Hiding the Names of the Days

In the Month view, the names of the days of the week are visible by default. You can hide the names by setting the `AreDayNamesVisible`(`bool`) property to `False`.

<snippet id='calendar-daynames-visibility'/>

> For a runnable example with the visibility of the names of the days in the Calendar, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **Calendar > Features** category.

## Hiding the Leading and Trailing Days

In the Month, Year, Century, and Decade views, the leading and trailing days are visible by default. You can hide them by setting the `IsOutOfScopeVisible`(`bool`) property to `False`.

<snippet id='calendar-outofscope-visibility'/>

> For a runnable example demonstrating the `IsOutOfScopeVisible` property, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **Calendar > Features** category.

## Setting the First Day of the Week

For half of the world, Monday is the first day of the week, and for the other half, this is Sunday. Use the `FirstDayOfWeek` property to set the first day of the week in your application.

 * `FirstDayOfWeek`(enum of type ` System.DayOfWeek?`)&mdash;Specifies the day that is considered the beginning of the week.

<snippet id='calendar-culture'/>


## See Also

- [Navigation]({%slug calendar-navigation%})
- [Formatting]({%slug calendar-date-formatting%})
- [Selection modes]({%slug calendar-selection%}) 
- [Events]({%slug calendar-events%})
- [Commands]({%slug calendar-commands%})
- [Templates]({%slug calendar-templates-overview%})
- [Styling]({%slug calendar-header-styling%})
