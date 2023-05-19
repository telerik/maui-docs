---
title: Navigation
page_title: .NET MAUI Calendar Documentation - Navigation
description: "Review the navigation options that Telerik Calendar for .NET MAUI control provides."
position: 9
slug: calendar-navigation
---

# .NET MAUI Calendar Navigation

Easily navigate to differnet calendar views or in the current view through the UI or programatically. This articvles explains all navigation options that the Calendar for .NET MAUI provides.

## Buttons for navigating the current view

The Calendar header has two buttons (previous and next) for navigating in the current view. For example in month view the previus button&mdash;navigates to the previous mont, next button&mdash;navigates to the next month.

![.NET MAUI Calendar navigation in the current view through the navigation buttons](images/combobox-header-footer.png)

## Navigating to upper view - through the UI

When tapping/clicking on the header label Calendar navigates to upper view.

![.NET MAUI Calendar navigation to upperview through the UI](images/combobox-header-footer.png)

## Restrict the navigation to upper or lower view

To restrict the navigation to upper or lower view use the following properties: 

* `MinDisplayMode`(`Telerik.Maui.controls.Calendar.CalendarDisplayMode`)&mdash;Specifies the minimum display mode of the calendar.
* `MaxDisplayMode`(`Telerik.Maui.controls.Calendar.CalendarDisplayMode`)&mdash;Specifies the maximum display mode of the calendar.

## Scroll Direction

You can scroll the calendar display mode hotrizontally or vertically. 

* `NavigationDirection`(enum of type `Telerik.Maui.Orientation`)&mdash;Specifies the scroll direction in the vieew mode of the calendar. The options are `Horizontal` and `Vertical`. Default is `Horizontal`.  

<snippet id='calendar-vertical-navigation'/>

![.NET MAUI Calendar scroll direction](images/combobox-header-footer.png)

> For the Calendar Navigation example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to Calendar -> Features category.

## Interaction Modes

Use the `InteractionMode`(enum of type `Telerik.Maui.Controls.Calendar.CalendarInteractionMode`) property of the Calendar to decide whether a navigation in the current view can be achieved through gesture. The available options are `None` and `Pan`. Default value is `Pan`.

>important The interaction is in the content part of the calendar. If you set the `InteractionMode` to `None`the users can navigate to next/previous in the current view by using the navigation buttons. 

> For the Calendar Interaction Mode example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to Calendar -> Features category.

![.NET MAUI Calendar interaction mode](images/combobox-header-footer.png)

## Commands

All commands for navigating to upper and lower view and in the current view are described in the [Calendar Commands]({%slug calendar-commands%}) article. 

## See Also

- [Display modes]({%slug calendar-display-modes%})
- [Formatting]({%slug calendar-date-formatting%})
- [Selection modes]({%slug calendar-selection%}) 
- [Events]({%slug calendar-events%})
- [Commands]({%slug calendar-commands%})
- [Templates]({%slug calendar-templates-overview%})
- [Styling]({%slug calendar-header-styling%})