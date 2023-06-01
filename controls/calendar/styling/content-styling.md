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

The `CalendarStyleSelector` class exposes the following properties: 

* `NormalLabelStyle`(of type `Style` with target type `telerik:CalendarLabel`)&mdash;
* `DisabledLabelStyle`(of type `Style` with target type `telerik:CalendarLabel`)&mdash;
* `OutOfScopeLabelStyle`(of type `Style` with target type `telerik:CalendarLabel`)&mdash;
* `SelectedBorderStyle`(of type `Style` with target type `telerik:CalendarBorderLabel`)&mdash;
* `TodayBorderStyle`(of type `Style` with target type `telerik:CalendarLabel`)&mdash;

* `DayNameLabelStyle`(of type `Style` with target type `Label`)&mdash;Specifies the style for the day names in the month views of the calendar.

## See Also

