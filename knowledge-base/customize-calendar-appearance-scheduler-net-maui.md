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
- How to style the day names in the drop-down calendar of the Scheduler?
- How to change the selection color in the calendar used by the Scheduler?
- How to modify text colors in the Scheduler's drop-down calendar?

## Solution

To customize the appearance of the drop-down calendar in the Telerik Scheduler for .NET MAUI, apply implicit styles targeting the `RadCalendar` component. Utilize a `DayStyleSelector` to define custom styles for different states of calendar labels such as normal, selected, and out-of-scope days.

**1.** Define `CustomCalendarStyleSelector` class which inherits from `CalendarStyleSelector` and override the `SelectStyle` method:

```C#
public class CustomCalendarStyleSelector : CalendarStyleSelector
{
    private Style customNormalLabelStyle;
    private Style customOutOfScopeLabelStyle;
    private Style customSelectedLabelStyle;
    private Style customSelectedMouseOverLabelStyle;
    private Style sundayMouseOverLabelStyle;
    private Style sundaySelectedLabelStyle;
    private Style sundaySelectedMouseOverLabelStyle;

    public override Style SelectStyle(object item, BindableObject container)
    {
        var node = (CalendarNode)item;
        var calendar = (RadCalendar)node.Calendar;
        bool isToday = node.IsToday;
        bool isSunday = calendar.DisplayMode == CalendarDisplayMode.Month && node.Date.Value.DayOfWeek == DayOfWeek.Sunday;
        bool isMouseOver = node.IsMouseOver;

        if (node.IsSelected)
        {
            return isMouseOver
                ? isSunday ? this.SundaySelectedMouseOverLabelStyle : this.CustomSelectedMouseOverLabelStyle
                : isSunday ? this.SundaySelectedLabelStyle : this.CustomSelectedLabelStyle;
        }

        if (isMouseOver)
        {
            return isSunday ? this.SundayMouseOverLabelStyle : base.SelectStyle(item, container);
        }

        if (isToday || !node.IsEnabled)
        {
            return base.SelectStyle(item, container);
        }

        if (node.IsOutOfScope)
        {
            return this.CustomOutOfScopeLabelStyle;
        }

        return isSunday ? this.SundayLabelStyle : this.CustomNormalLabelStyle;
    }

    public Style CustomNormalLabelStyle
    {
        get => customNormalLabelStyle;
        set
        {
            customNormalLabelStyle = value;
            customNormalLabelStyle.BasedOn = this.NormalLabelStyle;
        }
    }

    public Style CustomOutOfScopeLabelStyle
    {
        get => customOutOfScopeLabelStyle;
        set
        {
            customOutOfScopeLabelStyle = value;
            customOutOfScopeLabelStyle.BasedOn = this.OutOfScopeLabelStyle;
        }
    }

    public Style CustomSelectedLabelStyle
    {
        get => customSelectedLabelStyle;
        set
        {
            customSelectedLabelStyle = value;
            customSelectedLabelStyle.BasedOn = this.SelectedBorderStyle;
        }
    }

    public Style CustomSelectedMouseOverLabelStyle
    {
        get => customSelectedMouseOverLabelStyle;
        set
        {
            customSelectedMouseOverLabelStyle = value;
            customSelectedMouseOverLabelStyle.BasedOn = this.CustomSelectedLabelStyle;
        }
    }

    public Style SundayLabelStyle { get; set; }

    public Style SundayMouseOverLabelStyle
    {
        get => sundayMouseOverLabelStyle;
        set
        {
            sundayMouseOverLabelStyle = value;
            sundayMouseOverLabelStyle.BasedOn = this.SundayLabelStyle;
        }
    }

    public Style SundaySelectedLabelStyle
    {
        get => sundaySelectedLabelStyle;
        set
        {
            sundaySelectedLabelStyle = value;
            sundaySelectedLabelStyle.BasedOn = this.SundayLabelStyle;
        }
    }

    public Style SundaySelectedMouseOverLabelStyle
    {
        get => sundaySelectedMouseOverLabelStyle;
        set
        {
            sundaySelectedMouseOverLabelStyle = value;
            sundaySelectedMouseOverLabelStyle.BasedOn = this.SundayMouseOverLabelStyle;
        }
    }
}
```

**2.** Define a custom `DayStyleSelector` in the `ResourceDictionary` of your `ContentPage`. This selector allows specifying styles for various label states within the calendar.

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

**3.** Where the `local` is the `clr-namespace` where the `CustomCalendarStyleSelector` class is defined. 

**4.** Set the `RadCalendar.DayStyleSelector` property by using an implicit style:

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
