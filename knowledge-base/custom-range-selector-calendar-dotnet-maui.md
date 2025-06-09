---
title: Style the Range Selector for Calendar in .NET MAUI
description: Learn how to style the range selector for the Calendar component in .NET MAUI for the first, middle, and last selected dates.
type: how-to
page_title: Styling Calendar Range Selection in .NET MAUI
slug: custom-range-selector-calendar-dotnet-maui
tags: calendar, .net maui, range selection, styling, templates
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.0.0 | Telerik UI for .NET MAUI Calendar | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to create a custom range selector for the [Calendar](https://docs.telerik.com/devtools/maui/controls/calendar/overview) component in .NET MAUI with specific visual styling for the selected dates. The first and last selected dates should have semi-circular styles, while the middle dates should appear as rectangular blocks or connected backgrounds.

This knowledge base article also answers the following questions:
- How to style range selection in .NET MAUI Calendar?
- How to apply templates for selected dates in .NET MAUI Calendar?
- How to customize date styles in .NET MAUI Calendar?

## Solution

To achieve the desired styling for the Calendar component, define custom styles and use a `CalendarStyleSelector` as shown in the steps below:

**1.** Define custom styles in the XAML file for the first, middle, and last selected dates using the `CalendarBorderLabel` properties.

```xml
    <ContentPage.Resources>
        <ResourceDictionary>
            <local:CustomCalendarStyleSelector x:Key="DayStyleSelector">
                <local:CustomCalendarStyleSelector.CustomSelectedFirstStyle>
                    <Style TargetType="telerik:CalendarBorderLabel">
                        <Setter Property="TextColor" Value="#04A2AA" />
                        <Setter Property="FontAttributes" Value="Italic" />
                        <Setter Property="BorderThickness" Value="0" />
                        <Setter Property="BorderBackgroundColor" Value="#9AD9DD" />
                    </Style>
                </local:CustomCalendarStyleSelector.CustomSelectedFirstStyle>
                <local:CustomCalendarStyleSelector.CustomSelectedMiddleStyle>
                    <Style TargetType="telerik:CalendarBorderLabel">
                        <Setter Property="BorderThickness" Value="0" />
                        <Setter Property="BorderBackgroundColor" Value="LightCoral" />
                    </Style>
                </local:CustomCalendarStyleSelector.CustomSelectedMiddleStyle>
                <local:CustomCalendarStyleSelector.CustomSelectedLastStyle>
                    <Style TargetType="telerik:CalendarBorderLabel">
                        <Setter Property="TextColor" Value="White" />
                        <Setter Property="HorizontalTextAlignment" Value="Center" />
                        <Setter Property="BorderBackgroundColor" Value="Red" />
                        <Setter Property="BorderThickness" Value="0" />
                    </Style>
                </local:CustomCalendarStyleSelector.CustomSelectedLastStyle>
            </local:CustomCalendarStyleSelector>
        </ResourceDictionary>
    </ContentPage.Resources>
```

**2.** Link the styles to the Calendar in the XAML file:

```xml
    <telerik:RadCalendar x:Name="calendar" 
                         SelectionMode="Range"
                         DisplayMode="Month" 
                         DayStyleSelector="{StaticResource DayStyleSelector}" />
```

**3.** Implement the `CustomCalendarStyleSelector` class in the code-behind file to apply the styles based on the selection state.

```csharp
    public class CustomCalendarStyleSelector : CalendarStyleSelector
    {
        private Style customSelectedFirstStyle;
        private Style customSelectedMiddleStyle;
        private Style customSelectedLastStyle;

        public override Style SelectStyle(object item, BindableObject container)
        {
            var node = (CalendarNode)item;
            var calendar = (RadCalendar)node.Calendar;
            if (node.IsSelected && node.SelectionState == CalendarNodeSelectionState.First)
            {
                return this.CustomSelectedFirstStyle;
            }
            if (node.IsSelected && node.SelectionState == CalendarNodeSelectionState.Middle)
            {
                return this.CustomSelectedMiddleStyle;
            }
            if (node.IsSelected && node.SelectionState == CalendarNodeSelectionState.Last)
            {
                return this.CustomSelectedLastStyle;
            }
            return base.SelectStyle(item, container);
        }

        public Style CustomSelectedFirstStyle
        {
            get => customSelectedFirstStyle;
            set
            {
                customSelectedFirstStyle = value;
                customSelectedFirstStyle.BasedOn = this.SelectedBorderStyle;
            }
        }

        public Style CustomSelectedMiddleStyle
        {
            get => customSelectedMiddleStyle;
            set
            {
                customSelectedMiddleStyle = value;
                customSelectedMiddleStyle.BasedOn = this.SelectedBorderStyle;
            }
        }

        public Style CustomSelectedLastStyle
        {
            get => customSelectedLastStyle;
            set
            {
                customSelectedLastStyle = value;
                customSelectedLastStyle.BasedOn = this.SelectedBorderStyle;
            }
        }
    }
```

**4.** If you require more control over the borders or additional customization, use templates. Refer to the [Calendar Templates](https://docs.telerik.com/devtools/maui/controls/calendar/templates) documentation for more details.

## See Also

- [Calendar Overview](https://docs.telerik.com/devtools/maui/controls/calendar/overview)
- [Calendar Templates](https://docs.telerik.com/devtools/maui/controls/calendar/templates)
- [Calendar Selection](https://docs.telerik.com/devtools/maui/controls/calendar/selection)
