---
title: Overview
page_title: .NET MAUI Scheduler Documentation - Views
description: Learn more about the built-in views in the Telerik UI for .NET MAUI Scheduler control.
position: 0
slug: scheduler-views-overview
---

# Views Overview 

The Telerik UI for .NET MAUI Scheduler control provides the functionality of displaying the data in different views. The control defines four predefined views from which you can choose to navigate through. 

- [Day View]({%slug scheduler-day-view%})&mdash;Displays the appointments of a single day.
- [Week View]({%slug scheduler-week-view %})&mdash;Displays the appointment of a week.
- [Multiday View]({%slug scheduler-week-view %})&mdash;Displays the appointments of a specified number of days starting from `CurrentDate`.
- [Month View]({%slug scheduler-month-view %})&mdash;Displays the appointments of a month.
- [Agenda View]({%slug scheduler-agendaview-overview%})&mdash;Displays the appointments in a continuous, scrollable agenda list.

## Define the Views 

Define the available to the user views by adding them to the `ViewDefinitions` collection of the control. In addition, `ActiveViewDefinitionIndex` and `ActiveViewDefinition` properties are used to define the currently active view.

<snippet id='scheduler-getting-started-xaml'/>

## See Also

- [Day View]({%slug scheduler-day-view%})
- [Week View]({%slug scheduler-week-view %})
- [Multiday View]({%slug scheduler-week-view %})
- [Month View]({%slug scheduler-month-view %})
- [Agenda View]({%slug scheduler-agenda-view %})