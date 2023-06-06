---
title: Display Modes
page_title: .NET MAUI Calendar Documentation - Display Modes
description: "Calendar for .NET MAUI provides different display modes such as month, year, century, decade."
position: 2
slug: calendar-display-modes
---

# .NET MAUI Calendar Display Modes

The Telerik .NET MAUI Calendar is a control that displays a calendar representation from which the user can select a date. 
There are various display views that specify what is visible in the Calendar. The available views are month, year, decade, century.

## Setting the display mode programmatically

`DisplayMode` property(enum of type `Telerik.Maui.Controls.Calendar.CalendarDisplayMode`) defines the current view of RadCalendar control. The available display modes are:
* (Default)`Month`
* `Year`
* `Decade`
* `Century`

## Change the display mode through the UI

Easily change the `DisplayMode` throught the UI by tapping (for mobile) or clicking (for desktop) on the header text: 

![.NET MAUI Calendar Month View](images/combobox-header-footer.png)

## Setting min and max display mode

You can define a range for the display mode by using the 

* `MinDisplayMode`(enum of type `Telerik.Maui.Controls.Calendar.CalendarDisplayMode`)&mdash;Specifies the minimum display mode of the calendar. The available options are&mdash;`Month`, `Year`, `Decade`, `Century`. When `MinDisplayMode` is `Year`, you can select months from this year.
* `MaxDisplayMode`(enum of type `Telerik.Maui.Controls.Calendar.CalendarDisplayMode`)&mdash;Specifies the maximum display mode of the calendar. The available options are&mdash;`Month`, `Year`, `Decade`, `Century`.

<snippet id='calendar-display-range'/>

## Month view

This view represents all days in a single month.

<snippet id='calendar-displaymode-month'/>

![.NET MAUI Calendar Month View](images/display-mode-month.png)

## Year view

This view represents all months in a year.

<snippet id='calendar-displaymode-year'/>

![.NET MAUI Calendar Year View](images/display-mode-year.png)

## Decade view

This view represents all years in a decade.

<snippet id='calendar-displaymode-decade'/>

![.NET MAUI Calendar Decade View](images/display-mode-decade.png)

## Century view

This view represents all decades in a century.

<snippet id='calendar-displaymode-century'/>

![.NET MAUI Calendar Century View](images/display-mode-century.png)

> For all Calendar DisplayModes example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to Calendar -> Display Modes category.

## See Also

- [Navigation]({%slug calendar-navigation%})
- [Formatting]({%slug calendar-date-formatting%})
- [Selection modes]({%slug calendar-selection%}) 
- [Events]({%slug calendar-events%})
- [Commands]({%slug calendar-commands%})
- [Templates]({%slug calendar-templates-overview%})
- [Styling]({%slug calendar-header-styling%})