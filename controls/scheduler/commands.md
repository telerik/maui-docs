---
title: Commands
page_title: .NET MAUI Scheduler Documentation - Commands
description: Use the exposed commands of the Telerik UI for .NET MAUI Sheduler to programmatically navigate throught the dates.
position: 16
slug: scheduler-commands
---

# .NET MAUI Scheduler Commands

The Telerik UI for .NET MAUI Scheduler provides commands used to navigate through the view as well as commands that are executed on certain user actions, such as Appointment tap, Slot tap, etc.

## Navigation Commands

* `IncreaseVisibleRangeCommand` (`ICommand`)&mdash;Defines the command that is executed when the `RadScheduler` is navigated to the next date.

* `DecreaseVisibleRangeCommand` (`ICommand`)&mdash;Defines the command that is executed when the `RadScheduler` is navigated to the previous date.

* `TodayCommand` (`ICommand`)&mdash;Defines the command that is executed when the `RadScheduler` is navigated to today's date.

Check below a quick example on how to utilize navigation commands:

* **1.** Create a few buttons and execute the Scheduler commands on tap action:

<snippet id='scheduler-navigating-in-current-view' />

* **2.** Add a sample Scheduler definition:

<snippet id='scheduler-navigation-commands' />

## User Actions Commands

* `AppointmentTapCommand` (`ICommand`)&mdash;Defines the command that is executed when an appointment is tapped.

* `AppointmentDoubleTapCommand` (`ICommand`)&mdash;Defines the command that is executed when an appointment is double tapped.

* `SlotTapCommand` (`ICommand`)&mdash;Defines the command that executed when a slot is tapped.

* `SlotDoubleTapCommand` (`ICommand`)&mdash;Defines the command that is executed when a slot is double tapped.

* `MonthDayTapCommand` (`ICommand`)&mdash;Defines the command that is executed when a month day is tapped.

* `MonthDayDoubleTapCommand` (`ICommand`)&mdash;Defines the command that is executed when a a month day is double tapped.

## See Also

- [Header Visual Structure]({%slug scheduler-header-visual-structure%})
- [Appointments]({%slug appointments-overview%})
- [Views]({% slug scheduler-views-overview %})