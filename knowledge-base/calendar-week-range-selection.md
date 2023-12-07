---
title: How to select week range in .NET MAUI Calendar
description: Learn how to select week from Calendar when tapping on a day.
type: how-to
page_title: Week selection in .NET MAUI Calendar
slug: calendar-week-range-selection
position: 
tags: calendar, dotnet, maui, week selection, range selection
ticketid: 1627503
res_type: kb
---

## Environment
<table>
    <tbody>
        <tr>
            <td>Product</td>
            <td>Calendar for .NET MAUI</td>
        </tr>
    </tbody>
</table>


## Description

This article shows how to select a week in the Calendar for .NET MAUI when tapping/clicking on a date from this week. At the end you will receive the following result:

![.NET MAUI Calendar Week Selection](images/calendar-week-range-selection.gif)

## Solution

You need to define a Calendar and on `SelectionChanged` event implement the get the first day of week and then select the range for the whole week.

**1.** Calendar definition in XAML:

```XAML
<Grid>
    <telerik:RadCalendar x:Name="calendar"
                            HorizontalOptions="Center" 
                            VerticalOptions="Center"
                            SelectionMode="Range"
                            SelectionChanged="OnCalendarSelectionChanged" />
</Grid>
```

**2.** The `SelectionChanged` implementation:

```C#
public partial class MainPage : ContentPage
{
    private bool isInternalSelection = false;

    public MainPage()
    {
        InitializeComponent();
    }

    private void OnCalendarSelectionChanged(object sender, Telerik.Maui.Controls.Calendar.CalendarSelectionChangedEventArgs e)
    {
        if (this.isInternalSelection)
        {
            return;
        }

        var selectedDate = e.AddedDates.First();
        var culture = this.calendar.Culture ?? CultureInfo.CurrentCulture;
        var firstDayOfWeek = this.calendar.FirstDayOfWeek ?? culture.DateTimeFormat.FirstDayOfWeek;

        var rangeStart = this.GetFirstDayOfWeek(selectedDate, firstDayOfWeek);
        var rangeEnd = rangeStart.AddDays(6);

        var selectedDates = (CalendarSelectionCollection)this.calendar.SelectedDates;

        this.isInternalSelection = true;
        selectedDates.AddRange(rangeStart, rangeEnd);
        this.isInternalSelection = false;
    }

    private DateTime GetFirstDayOfWeek(DateTime dateTime, DayOfWeek weekStart)
    {
        var selectedDay = (int)dateTime.DayOfWeek;
        if (selectedDay < (int)weekStart)
        {
            selectedDay += 7;
        }

        int daysToSubtract = selectedDay - (int)weekStart;
        DateTime result = dateTime.AddDays(-daysToSubtract);
        return result;
    }
}
```