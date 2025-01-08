---
title: Styling the Calendar in Telerik Scheduler for .NET MAUI
description: Learn how to customize the appearance of the drop-down calendar in Telerik Scheduler for .NET MAUI by changing text and selection colors.
type: how-to
page_title: Customizing Calendar Appearance in Telerik Scheduler for .NET MAUI
slug: customize-calendar-appearance-scheduler-net-maui
tags: calendar, styling, scheduler, .net maui, text color, selection color
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 9.0.0 | Telerik UI for .NET MAUI Scheduler | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

## Description

In Telerik Scheduler for .NET MAUI, you may need to change the text and selection colors of the drop-down calendar.

This knowledge base article also answers the following questions:
- How to style the day names in the drop-down calendar of Scheduler?
- How to change the selection color in the calendar used by Scheduler?
- How to modify text colors in the Scheduler's drop-down calendar?

## Solution

To customize the appearance of the drop-down calendar in the Telerik Scheduler for .NET MAUI, apply implicit styles targeting the `RadCalendar` component. Utilize a `DayStyleSelector` to define custom styles for different states of calendar labels such as normal, selected, and out-of-scope days.

**1.** Define a custom `DayStyleSelector` in the `ResourceDictionary` of your `ContentPage`. This selector allows specifying styles for various label states within the calendar.

```xml
<local:CustomCalendarStyleSelector x:Key="DayStyleSelector">
    <local:CustomCalendarStyleSelector.CustomSelectedLabelStyle>
        <Style TargetType="telerik:CalendarBorderLabel">
            <Setter Property="TextColor" Value="#04A2AA" />
            <Setter Property="FontAttributes" Value="Italic" />
            <Setter Property="BorderThickness" Value="0" />
            <Setter Property="BorderBackgroundColor" Value="#9AD9DD" />
        </Style>
    </local:CustomCalendarStyleSelector.CustomSelectedLabelStyle>
    <local:CustomCalendarStyleSelector.CustomSelectedMouseOverLabelStyle>
        <Style TargetType="telerik:CalendarBorderLabel">
            <Setter Property="BorderBackgroundColor" Value="#B3E3E5" />
        </Style>
    </local:CustomCalendarStyleSelector.CustomSelectedMouseOverLabelStyle>
    <local:CustomCalendarStyleSelector.CustomOutOfScopeLabelStyle>
        <Style TargetType="telerik:CalendarLabel">
            <Setter Property="TextColor" Value="#6104A2AA" />
        </Style>
    </local:CustomCalendarStyleSelector.CustomOutOfScopeLabelStyle>
    <local:CustomCalendarStyleSelector.CustomNormalLabelStyle>
        <Style TargetType="telerik:CalendarLabel">
            <Setter Property="TextColor" Value="#04A2AA" />
        </Style>
    </local:CustomCalendarStyleSelector.CustomNormalLabelStyle>
    <local:CustomCalendarStyleSelector.SundayLabelStyle>
        <Style TargetType="telerik:CalendarBorderLabel">
            <Setter Property="TextColor" Value="#FF9040" />
            <Setter Property="HorizontalTextAlignment" Value="Center" />
        </Style>
    </local:CustomCalendarStyleSelector.SundayLabelStyle>
    <local:CustomCalendarStyleSelector.SundayMouseOverLabelStyle>
        <Style TargetType="telerik:CalendarBorderLabel">
            <Setter Property="BorderBackgroundColor" Value="#FFE8D8" />
        </Style>
    </local:CustomCalendarStyleSelector.SundayMouseOverLabelStyle>
    <local:CustomCalendarStyleSelector.SundaySelectedLabelStyle>
        <Style TargetType="telerik:CalendarBorderLabel">
            <Setter Property="BorderBackgroundColor" Value="#FFDDC5" />
        </Style>
    </local:CustomCalendarStyleSelector.SundaySelectedLabelStyle>
    <local:CustomCalendarStyleSelector.SundaySelectedMouseOverLabelStyle>
        <Style TargetType="telerik:CalendarBorderLabel" />
    </local:CustomCalendarStyleSelector.SundaySelectedMouseOverLabelStyle>
 </local:CustomCalendarStyleSelector>
```

**2.** Set the `RadCalendar.DayStyleSelector` property by using an implicit style:

```XAML
<Style TargetType="telerik:RadCalendar" >
    <Setter Property="DayStyleSelector" Value="{StaticResource DayStyleSelector}" />
</Style>
```

**3.** Apply the `RadScheduler` to your `ContentPage` and set its `CurrentDate` and `ViewDefinitions` as needed. The custom styles defined in the `DayStyleSelector` will automatically apply to the drop-down calendar.

```xml
<telerik:RadScheduler AutomationId="scheduler" CurrentDate="10/18/2023">
    <telerik:RadScheduler.ViewDefinitions>
        <!-- View definitions for the scheduler -->
    </telerik:RadScheduler.ViewDefinitions>
</telerik:RadScheduler>
```

By following these steps, you can effectively change the text and selection colors of the drop-down calendar used in the Telerik Scheduler for .NET MAUI, enhancing the visual consistency and user experience of your application.

## See Also

- [Day Styling in Telerik Calendar for .NET MAUI](https://docs.telerik.com/devtools/maui/controls/calendar/styling/day-styling)
- [Scheduler Overview for .NET MAUI](https://docs.telerik.com/devtools/maui/controls/scheduler/overview)
- [Calendar Overview for .NET MAUI](https://docs.telerik.com/devtools/maui/controls/calendar/overview)
