---
title: Styling Day Numbers and Day Names in Month View in Scheduler for .NET MAUI
description: Learn how to change the position and style of day numbers and day names in the Month View of the Scheduler for .NET MAUI.
type: how-to
page_title: Customizing Day Numbers and Day Names in Scheduler Month View in .NET MAUI
meta_title: Customizing Day Numbers and Day Names in Scheduler Month View in .NET MAUI
slug: customize-day-numbers-and-day-names-scheduler-month-view-dotnet-maui
tags: scheduler, monthview, daystyling, daynamestyling, scheduler .net maui
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.0.1 | Scheduler for .NET MAUI | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to change the position of the day numbers to the start of the month view box in the Scheduler for .NET MAUI. I also want to change the style of the day names in the Month View.

This knowledge base article also answers the following questions:
- How to style day numbers in the Scheduler for .NET MAUI Month View?
- How to customize day names in the Scheduler for .NET MAUI Month View?
- How to use style selectors for day elements in the Scheduler for .NET MAUI?

## Solution

To style day numbers and day names in the Month View, use the `DayStyleSelector` and `DayNameStyleSelector` properties of the [Scheduler Month View](https://docs.telerik.com/devtools/maui/controls/scheduler/views/month-view).

**1.** Define custom styles in the `DayStyleSelector` and `DayNameStyleSelector`. Use the following XAML:

```xaml
<ContentPage.Resources>
    <ResourceDictionary>
        <local:CustomDayStyleSelector x:Key="CustomDayStyleSelector">
            <local:CustomDayStyleSelector.CustomNormalStyle>
                <Style TargetType="Label">
                    <Setter Property="TextColor" Value="#018383" />
                    <Setter Property="HorizontalTextAlignment" Value="Center" />
                    <Setter Property="VerticalTextAlignment" Value="Center" />
                </Style>
            </local:CustomDayStyleSelector.CustomNormalStyle>
            <local:CustomDayStyleSelector.CustomTodayStyle>
                <Style TargetType="Label">
                    <Setter Property="TextColor" Value="#830183" />
                    <Setter Property="FontAttributes" Value="Bold" />
                    <Setter Property="HorizontalTextAlignment" Value="Center" />
                    <Setter Property="VerticalTextAlignment" Value="Center" />
                </Style>
            </local:CustomDayStyleSelector.CustomTodayStyle>
            <local:CustomDayStyleSelector.WeekendLabelStyle>
                <Style TargetType="Label">
                    <Setter Property="TextColor" Value="#707070" />
                    <Setter Property="HorizontalTextAlignment" Value="Center" />
                    <Setter Property="VerticalTextAlignment" Value="Center" />
                </Style>
            </local:CustomDayStyleSelector.WeekendLabelStyle>
        </local:CustomDayStyleSelector>
    </ResourceDictionary>
</ContentPage.Resources>

<telerik:RadScheduler x:Name="scheduler" ActiveViewDefinitionIndex="1">
    <telerik:RadScheduler.ViewDefinitions>
        <telerik:MonthViewDefinition DayNameStyleSelector="{StaticResource CustomDayStyleSelector}" 
                                      DayStyleSelector="{StaticResource CustomDayStyleSelector}" />
    </telerik:RadScheduler.ViewDefinitions>
</telerik:RadScheduler>
```

**2.** Define the style selector classes. Use custom logic in the selector to style specific days, such as weekends or the current day.

```csharp
public class CustomDayStyleSelector : DayStyleSelector
{
    private Style customNormalStyle;
    private Style customTodayStyle;
    private Style weekendLabelStyle;

    public override Style SelectStyle(object item, BindableObject bindable)
    {
        var node = (DateNode)item;
        if (node.IsToday)
        {
            return this.customTodayStyle;
        }

        var date = node.Date;
        if (date.DayOfWeek == DayOfWeek.Saturday || date.DayOfWeek == DayOfWeek.Sunday)
        {
            return this.weekendLabelStyle;
        }

        return this.customNormalStyle;
    }

    public Style CustomNormalStyle
    {
        get => this.customNormalStyle;
        set
        {
            this.customNormalStyle = value;
            this.customNormalStyle.BasedOn = this.NormalLabelStyle;
        }
    }

    public Style CustomTodayStyle
    {
        get => this.customTodayStyle;
        set
        {
            this.customTodayStyle = value;
            this.customTodayStyle.BasedOn = this.TodayLabelStyle;
        }
    }

    public Style WeekendLabelStyle
    {
        get => this.weekendLabelStyle;
        set
        {
            this.weekendLabelStyle = value;
            this.weekendLabelStyle.BasedOn = this.NormalLabelStyle;
        }
    }
}
```


## See Also
- [Scheduler Month View Overview](https://docs.telerik.com/devtools/maui/controls/scheduler/views/month-view)
- [Day Styling Documentation](https://docs.telerik.com/devtools/maui/controls/scheduler/styling/day-styling)
