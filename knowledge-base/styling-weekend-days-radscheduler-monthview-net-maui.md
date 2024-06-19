---
title: Styling Weekend Days in the Scheduler Month View
description: Learn how to style weekend days differently from weekdays in the Month View of Telerik UI for .NET MAUI Scheduler.
type: how-to
page_title: How to Style Weekend Days in RadScheduler Month View for .NET MAUI
slug: styling-weekend-days-radscheduler-monthview-net-maui
tags: calendar, .net maui, radscheduler, monthview, daystyleselector, weekend styling
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 7.0.0 | Telerik UI for .NET MAUI Scheduler | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

## Description

When using the Telerik UI `RadScheduler` in a .NET MAUI application, I want to style the weekend days differently from the weekdays in the `MonthView`. Initially, I wanted to use the `SpecialSlotStyleSelector` for the `MonthViewDefinition` from Telerik Xamarin Scheduler, but it's not available in the Telerik UI for .NET MAUI Scheduler. How can I style my weekend days differently in the month view?

This KB article also answers the following questions:
- How can I apply custom styling to weekend days in the Scheduler `MonthView`?
- Is there a way to differentiate weekend and weekday styles in .NET MAUI Scheduler?
- What property should be used for day styling in `MonthViewDefinition` of `RadScheduler`?

## Solution

To style days differently in the `MonthView` of `RadScheduler` for .NET MAUI, instead of using `SpecialSlotStyleSelector`, you should utilize the `DayStyleSelector`. This allows for custom styling of days, including differentiating weekends from weekdays.

First, ensure the Scheduler is set to use the `MonthView`:

```xml
<telerik:RadScheduler x:Name="scheduler" ActiveViewDefinitionIndex="1">
    <telerik:RadScheduler.ViewDefinitions>
        <telerik:MonthViewDefinition DayStyleSelector="{StaticResource CustomDayStyleSelector}" />
    </telerik:RadScheduler.ViewDefinitions>
</telerik:RadScheduler>
```

Next, to specifically style the weekends, you can define a `WeekendLabelStyle` within your `CustomDayStyleSelector`. Here's how you can set the background color for weekend days:

```xml
<local:CustomDayStyleSelector.WeekendLabelStyle>
    <Style TargetType="Label">
        <Setter Property="TextColor" Value="#707070" />
        <Setter Property="HorizontalTextAlignment" Value="Center" />
        <Setter Property="VerticalTextAlignment" Value="Center" />
    </Style>
</local:CustomDayStyleSelector.WeekendLabelStyle>
```

This approach allows for a high degree of customization for day styling within the `MonthView` of `RadScheduler`.

For more details and examples on how to further customize the Scheduler, refer to the [RadScheduler Day Styling]({%slug scheduler-day-styling%}) and explore the Scheduler examples in the [SDK Browser application]({%slug sdkbrowser-app%}) and [Controls Samples application]({%slug controls-samples-app%}).

---
