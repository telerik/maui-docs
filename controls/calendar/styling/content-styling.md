---
title: Content Styling
page_title: .NET MAUI ComboBox Documentation - Content Styling
description: ""
position: 2
slug: calendar-content-styling
---

# .NET MAUI Calendar Content Styling

Calendar control for .NET MAUI provides the following Style properties for customizing the look of its content:

* `DayStyleSelector`(of type `CalendarStyleSelector`)&mdash;Specifies the style selector for the days in the month views of the calendar.
* `MonthStyleSelector`(of type `CalendarStyleSelector`)&mdash;Specifies the style selector for the month views in the year views of the calendar.
* `YearStyleSelector`(of type `CalendarStyleSelector`)&mdash;Specifies the style selector for the year views in the decade view of the calendar.
* `DecadeStyleSelector`(of type `CalendarStyleSelector`)&mdash;Specifies the style selector for the decade views in the century view of the calendar.

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

>important When inherits from `CalendarStyleSelector`, override the `SelectStyle` method and cast the `object item` to `CalendarNode`. The `CalendarNode` is the model that is visualized in the calendar's views.

The `CalendarNode` class has the information for:

* The `date` each node holds and gets displayes in the calendar's view.
* `text` that is displayed in the calendar's view.
* `IsSelected`(`bool`)&mdash;gets a value indicating whether the node is selected
* `IsEnabled`(`bool`)&mdash;Gets a value indicating whether the node is enabled.
* `IsOutOfScope`(`bool`)&mdash;Gets a value indicating whether the node is out of scope.
* `IsToday`(`bool`)&mdash;Gets a value indicating whether the date is today.
* `IsMouseOver`(`bool`)&mdash;Gets a value indicating whether the mouse is over the date.
* `IsVisible`(`bool`)&mdash;Gets a value indicating whether the node is visible.
* `SelectionState`(enum of type `Telerik.Maui.controls.Calendar.CalendarNodeSelectionState`)&mdash;Gets a value indicating the state of the date when selected. The options are: `None`, `Single`, `Middle`, `First` and `Last`.

The `CustomStyleSelector` class that inherits from `CalendarStyleSelector`

<snippet id='calendar-styleselectors-custom-calendarstyleselector'/>

## See Also

