---
title: Display Modes
page_title: .NET MAUI Calendar Documentation - Display Modes
description: The Calendar for .NET MAUI provides several display modes such as month, year, century, and decade. Learn how to control these display modes.
components: ["calendar"]
position: 2
slug: calendar-display-modes
---

# .NET MAUI Calendar Display Modes

The Telerik <a href="https://www.telerik.com/maui-ui/calendar" target="_blank">.NET MAUI Calendar</a> is a control that allows the user to select a date from a standard view that can represent various time spans. The Calendar views define what is visible in the Calendar, for example, month, year, decade, or century.

## Setting the Display Mode Programmatically

The `DisplayMode` property (enum of type `Telerik.Maui.Controls.Calendar.CalendarDisplayMode`) defines the current view of the `RadCalendar` control. The available display modes are:

* `Month` (Default)
* `Year`
* `Decade`
* `Century`

## Changing the Display Mode through the UI

The user can effortlessly change the `DisplayMode` through the UI by tapping (for mobile) or clicking (for desktop) the header text.

![Telerik UI for .NET MAUI Calendar changing display modes through the header label](images/calendar-change-display-mode.gif)

## Setting Min and Max Display Mode

You can define a range of display modes that will be available to the user through the following properties:

* `MinDisplayMode` (enum of type `Telerik.Maui.Controls.Calendar.CalendarDisplayMode`)&mdash;Specifies the minimum display mode of the Calendar. The available options are `Month`, `Year`, `Decade`, and `Century`. When `MinDisplayMode` is `Year`, users can select months from this year.
* `MaxDisplayMode` (enum of type `Telerik.Maui.Controls.Calendar.CalendarDisplayMode`)&mdash;Specifies the maximum display mode of the Calendar. The available options are `Month`, `Year`, `Decade`, and `Century`.

<snippet id='calendar-display-range'/>

## Month View

The month view represents all days in a single month.

<snippet id='calendar-displaymode-month'/>

![Telerik UI for .NET MAUI Calendar Month display mode showing the days of June 2023](images/display-mode-month.png)

## Year View

The year view represents all months in a year.

<snippet id='calendar-displaymode-year'/>

![Telerik UI for .NET MAUI Calendar Year display mode showing the twelve months of 2023](images/display-mode-year.png)

## Decade View

The decade view represents all years in a decade.

<snippet id='calendar-displaymode-decade'/>

![Telerik UI for .NET MAUI Calendar Decade display mode showing the years 2019 through 2030](images/display-mode-decade.png)

## Century View

The century view represents all decades in a century.

<snippet id='calendar-displaymode-century'/>

![Telerik UI for .NET MAUI Calendar Century display mode showing decade ranges from 1990 through 2110](images/display-mode-century.png)

> For all examples with the display modes of the Calendar, check the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **Calendar > Display Modes** category.

## See Also

- [Navigation Between the Different Views]({%slug calendar-navigation%})
- [Specify the Formatting]({%slug calendar-date-formatting%})
- [Selection modes]({%slug calendar-selection%}) 
- [Use exposed Events]({%slug calendar-events%})
- [Use the exposed Commands]({%slug calendar-commands%})
- [Define Templates]({%slug calendar-templates-overview%})
- [Calendar Header Styling]({%slug calendar-header-styling%})
