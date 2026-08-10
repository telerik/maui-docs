---
title: Switching Visible Time Range Between Full Day and Work Hours in UI for .NET MAUI Scheduler
description: Learn how to switch the visible time range between full day view and work hours in the Scheduler for UI for .NET MAUI.
type: how-to
page_title: Adjusting Scheduler Time Range for Full Day and Work Hours in .NET MAUI
meta_title: Adjusting Scheduler Time Range for Full Day and Work Hours in .NET MAUI
slug: scheduler-switch-visible-time-range
tags: scheduler, ui-for-dotnet-maui, daystarttime, dayendtime
res_type: kb
---

## Environment

| Version | Product | Author |
| --- | ---- | ---- |
| 14.1.0 | Telerik UI for .NET MAUI Scheduler | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

I want to adjust the visible time range in the [Scheduler](https://docs.telerik.com/devtools/maui/controls/scheduler/overview) for UI for .NET MAUI. By default, the Scheduler displays the full day (00:00–24:00), but I need it to show only work hours (08:00–17:00) with the ability to switch back to the full day view.

This knowledge base article also answers the following questions:
- How do I configure work hours in the Scheduler for .NET MAUI?
- How can I toggle between full day and work hours in the Scheduler control?
- How to use DayStartTime and DayEndTime properties in the Scheduler for UI for .NET MAUI?

## Solution

To toggle the visible time range between a full day and work hours, use the `DayStartTime` and `DayEndTime` properties of the `MultidayViewDefinition`, `DayViewDefinition`, and `WeekViewDefinition`. Bind these properties to a view model for dynamic updates.

1. Define the Scheduler in XAML:

```xml
<Grid RowDefinitions="Auto,*" Padding="8" RowSpacing="8">
    <HorizontalStackLayout Grid.Row="0" Spacing="8" VerticalOptions="Center">
        <telerik:RadCheckBox x:Name="fullDayCheckBox"
                             IsChecked="{Binding IsFullDay, Mode=TwoWay}"
                             VerticalOptions="Center" />
        <Label Text="Show full day (00:00 - 24:00)" VerticalOptions="Center" />
    </HorizontalStackLayout>

    <telerik:RadScheduler x:Name="scheduler" Grid.Row="1">
        <telerik:RadScheduler.ViewDefinitions>
            <telerik:MultidayViewDefinition x:Name="dayview" VisibleDays="3"
                                            DayStartTime="{Binding DayStartTime, Mode=TwoWay}"
                                            DayEndTime="{Binding DayEndTime, Mode=TwoWay}" />
            <telerik:MonthViewDefinition />
            <telerik:DayViewDefinition DayStartTime="{Binding DayStartTime, Mode=TwoWay}"
                                        DayEndTime="{Binding DayEndTime, Mode=TwoWay}" />
        </telerik:RadScheduler.ViewDefinitions>
    </telerik:RadScheduler>
</Grid>
```

2. Define a sample `ViewModel`:

```csharp
public class ViewModel : NotifyPropertyChangedBase
{
    private static readonly TimeOnly WorkingDayStart = new(8, 0, 0);
    private static readonly TimeOnly WorkingDayEnd = new(17, 0, 0);
    private static readonly TimeOnly FullDayStart = new(0, 0, 0);
    private static readonly TimeOnly FullDayEnd = new(23, 59, 59);

    private TimeOnly dayStartTime = WorkingDayStart;
    private TimeOnly dayEndTime = WorkingDayEnd;
    private bool isFullDay;

    public bool IsFullDay
    {
        get => this.isFullDay;
        set
        {
            if (this.isFullDay != value)
            {
                this.isFullDay = value;
                this.OnPropertyChanged();

                this.DayStartTime = value ? FullDayStart : WorkingDayStart;
                this.DayEndTime = value ? FullDayEnd : WorkingDayEnd;
            }
        }
    }

    public TimeOnly DayStartTime
    {
        get => this.dayStartTime;
        set
        {
            if (this.dayStartTime != value)
            {
                this.dayStartTime = value;
                this.OnPropertyChanged();
            }
        }
    }

    public TimeOnly DayEndTime
    {
        get => this.dayEndTime;
        set
        {
            if (this.dayEndTime != value)
            {
                this.dayEndTime = value;
                this.OnPropertyChanged();
            }
        }
    }
}
```

3. Set the binding context:

```csharp
public partial class SchedulerPage : ContentPage
{
    public SchedulerPage()
    {
        InitializeComponent();
        this.BindingContext = new ViewModel();
    }
}
```

## See Also

- [Scheduler Overview](https://docs.telerik.com/devtools/maui/controls/scheduler/overview)
- [Scheduler View Definitions](https://www.telerik.com/maui-ui/documentation/controls/scheduler/views/overview)
