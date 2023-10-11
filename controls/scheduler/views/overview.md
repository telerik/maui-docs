---
title: Views Overview
page_title: .NET MAUI Scheduler Documentation - Views
description: Learn more about the built-in views in the Telerik UI for .NET MAUI Scheduler control.
position: 0
slug: scheduler-views-overview
---

# Views Overview 

The Telerik UI for .NET MAUI Scheduler control provides the functionality of displaying the data in different views. The control defines four predefined views from which you can choose to navigate through. 

* `DayViewDefinition`
* `WeekViewDefinition`
* `MultidayViewDefinition`
* `MonthViewDefinition`

## Define the Views 

Define the available to the user views by adding them to the `ViewDefinitions` collection of the control. In addition, `ActiveViewDefinitionIndex` and `ActiveViewDefinition` properties are used to define the currently active view.

<snippet id='scheduler-getting-started-xaml'/>
