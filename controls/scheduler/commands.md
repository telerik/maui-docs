---
title: Commands
page_title: .NET MAUI Scheduler Documentation - Commands
description: Use the exposed commands of the Telerik UI for .NET MAUI Sheduler to programmatically navigate throught the dates.
position: 8
slug: scheduler-commands
---

# .NET MAUI Scheduler Commands

The Telerik UI for .NET MAUI Scheduler provides commands used to navigate through the view as well as commands that are executed on certain user actions, such as Appointment tap, Slot tap, etc.

## Navigation Commands

* `IncreaseCurrentDateCommand` (`ICommand`)&mdash;Defines the command that is executed when the `RadScheduler` is navigated to the next date.

* `DecreaseCurrentDateCommand` (`ICommand`)&mdash;Defines the command that is executed when the `RadScheduler` is navigated to the previous date.

* `NavigateToTodayCommand` (`ICommand`)&mdash;Defines the command that is executed when the `RadScheduler` is navigated to today date.

Check below a quick example on how to utilize navigation commands:



## User Actions Commands

* `AppointmentTapCommand` (`ICommand`)&mdash;Defines the command that is executed when an appointment is tapped.

* `AppointmentDoubleTapCommand` (`ICommand`)&mdash;Defines the command that is executed when an appointment is double tapped.

* `SlotTapCommand` (`ICommand`)&mdash;Defines the command that executed when a slot is tapped.

* `SlotDoubleTapCommand` (`ICommand`)&mdash;Defines the command that is executed when a slot is double tapped.

* `MonthDayTapCommand` (`ICommand`)&mdash;Defines the command that is executed when a month day is tapped.

* `MonthDayDoubleTapCommand` (`ICommand`)&mdash;Defines the command that is executed when a a month day is double tapped.
