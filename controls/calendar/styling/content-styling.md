---
title: Content Styling
page_title: .NET MAUI Calendar Documentation - Content Styling
description: Learn what styling options are available for the content area of the Telerik UI for .NET MAUI Calendar control. Find out how to use the styling options to customize the appearance of the UI component.
position: 2
slug: calendar-content-styling
---

# .NET MAUI Calendar Content Styling

The Calendar control for .NET MAUI provides the following styling properties for customizing the appearance of its content:

* `DayStyleSelector`(of type `CalendarStyleSelector`)&mdash;Specifies the style selector for the days in the month view of the Calendar.
* `MonthStyleSelector`(of type `CalendarStyleSelector`)&mdash;Specifies the style selector for the months in the year view of the Calendar.
* `YearStyleSelector`(of type `CalendarStyleSelector`)&mdash;Specifies the style selector for the years in the decade view of the Calendar.
* `DecadeStyleSelector`(of type `CalendarStyleSelector`)&mdash;Specifies the style selector for the decades in the century view of the Calendar.

The `CalendarStyleSelector` class exposes the following properties listed in the table below: 

| CalendarStyleSelector | Description |
| ------------- | --------------- |
| `NormalLabelStyle`(of type `Style` with target type `telerik:CalendarLabel`) | Gets the style applied to the `CalendarLabel` when in normal state. |
| `DisabledLabelStyle`(of type `Style` with target type `telerik:CalendarLabel`) | Gets the style applied to the `CalendarLabel` when in disabled state. |
| `OutOfScopeLabelStyle`(of type `Style` with target type `telerik:CalendarLabel`) | Gets the style applied to the `CalendarLabel` when in out of scope state. |
| `SelectedBorderStyle`(of type `Style` with target type `telerik:CalendarBorderLabel`) | Gets the style applied to the `CalendarBorderLabel` when the date is selected. |
| `MouseOverBorderStyle`(of type `Style` with target type `telerik:CalendarBorderLabel`) | Gets the style applied to the `CalendarBorderLabel` when the date has the mouse over it. |
| `SelectedMouseOverBorderStyle`(of type `Style` with target type `telerik:CalendarBorderLabel`) | Gets the style applied to the `CalendarBorderLabel` when the date has the mouse over it and is selected. |
| `TodayBorderStyle`(of type `Style` with target type `telerik:CalendarBorderLabel`) | Gets the style applied to the `CalendarBorderLabel` for the today date. |
| `TodayMouseOverBorderStyle`(of type `Style` with target type `telerik:CalendarBorderLabel`) | Gets the style applied to the `CalendarBorderLabel` for the date that has the mouse over it and is today. |
| `TodaySelectedBorderStyle`(of type `Style` with target type `telerik:CalendarBorderLabel`) | Gets the style applied to the `CalendarBorderLabel` when the today date is selected. |
| `TodaySelectedMouseOverBorderStyle`(of type `Style` with target type `telerik:CalendarBorderLabel`) | Gets the style applied to the `CalendarBorderLabel` for the date that has the mouse over it, is today and it is selected. |
| `TodayFirstInRangeBorderStyle`(of type `Style` with target type `telerik:CalendarBorderLabel`) | Gets the style applied to the `CalendarBorderLabel` for the today date when selected and is first in range. |
| `TodayFirstInRangeMouseOverBorderStyle`(of type `Style` with target type `telerik:CalendarBorderLabel`) | Gets the style applied to the `CalendarBorderLabel` for the today date when selected and mouse over and is first in range. |
| `TodayMiddleInRangeBorderStyle`(of type `Style` with target type `telerik:CalendarBorderLabel`) | Gets the style applied to the `CalendarBorderLabel` for the today date when selected and is middle in range. |
| `TodayMiddleInRangeMouseOverBorderStyle`(of type `Style` with target type `telerik:CalendarBorderLabel`) | Gets the style applied to the `CalendarBorderLabel` for the today date when selected and mouse over and is middle in range. |
| `TodayLastInRangeBorderStyle`(of type `Style` with target type `telerik:CalendarBorderLabel`) | Gets the style applied to the `CalendarBorderLabel` for the today date when selected and is last in range. |
| `TodayLastInRangeMouseOverBorderStyle`(of type `Style` with target type `telerik:CalendarBorderLabel`) | Gets the style applied to the `CalendarBorderLabel` for the today date when selected and mouse over and is last in range. |
| `FirstInRangeBorderStyle`(of type `Style` with target type `telerik:CalendarBorderLabel`) | Gets the style applied to the `CalendarBorderLabel` for the selected date when is first in range. |
| `FirstInRangeMouseOverBorderStyle`(of type `Style` with target type `telerik:CalendarBorderLabel`) | Gets the style applied to the `CalendarBorderLabel` for the selected date that has the mouse over it and it is first in range selection. |
| `MiddleInRangeBorderStyle`(of type `Style` with target type `telerik:CalendarBorderLabel`) | Gets the style applied to the `CalendarBorderLabel` for the selected date when is middle in range. |
| `MiddleInRangeMouseOverBorderStyle`(of type `Style` with target type `telerik:CalendarBorderLabel`) | Gets the style applied to the `CalendarBorderLabel` for the selected date that has the mouse over it and it is middle in range selection. |
| `LastInRangeBorderStyle`(of type `Style` with target type `telerik:CalendarBorderLabel`) | Gets the style applied to the `CalendarBorderLabel` for the selected date when is last in range. |
| `LastInRangeMouseOverBorderStyle`(of type `Style` with target type `telerik:CalendarBorderLabel`) | Gets the style applied to the `CalendarBorderLabel` for the selected date that has the mouse over it and it is last in range selection |

>important When inheriting from `CalendarStyleSelector`, override the `SelectStyle` method and cast the `object item` to `CalendarNode`. The `CalendarNode` is the model that is visualized in the Calendar's views.

The `CalendarNode` class has the information for:

* `date`&mdash;The date that each node holds and that gets displayed in the Calendar's view.
* `Text`&mdash;The text that is displayed in the Calendar's view.
* `IsSelected`(`bool`)&mdash;Gets a value indicating whether the node is selected
* `IsEnabled`(`bool`)&mdash;Gets a value indicating whether the node is enabled.
* `IsOutOfScope`(`bool`)&mdash;Gets a value indicating whether the node is out of scope.
* `IsToday`(`bool`)&mdash;Gets a value indicating whether the date is today.
* `IsMouseOver`(`bool`)&mdash;Gets a value indicating whether the mouse is over the date.
* `IsVisible`(`bool`)&mdash;Gets a value indicating whether the node is visible.
* `SelectionState`(enum of type `Telerik.Maui.controls.Calendar.CalendarNodeSelectionState`)&mdash;Gets a value indicating the state of the date when selected. The options are: `None`, `Single`, `Middle`, `First` and `Last`.

The following example demonstrates the `CustomStyleSelector` class that inherits from `CalendarStyleSelector`:

<snippet id='calendar-styleselectors-custom-calendarstyleselector'/>
