---
title: Customizing Header Settings in RadScheduler for .NET MAUI
description: Learn how to modify the RadScheduler header, including removing navigation buttons and aligning the month text.
type: how-to
page_title: How to Customize Header in Telerik RadScheduler for .NET MAUI
slug: customize-header-rad-scheduler-net-maui
tags: scheduler, .net maui, header, customize, alignment, navigation button, visible views button
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 7.0.0 | Telerik UI for .NET MAUI Scheduler | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

## Description

I need to modify the RadScheduler header to better suit my application's UI. How can I achieve the following Telerik UI for .NET MAUI Scheduler customizations?

* Remove the drop-down navigation button located at the top left of the header, which opens the calendar, but retain the month text (e.g., Jun 2024). 
* Center the month text within the header.
* Hide the "Available views" button located at the header's top right.

This KB article also answers the following questions:
- How to remove the navigation button from the RadScheduler header?
- How to center the header text in RadScheduler?
- How to hide the "Available views" button in RadScheduler?

## Solution

To customize the header of the [RadScheduler]({%slug scheduler-overview%}) for .NET MAUI, including removing the navigation button, aligning the month text, and hiding the "Available views" button, you can use a control template. The steps below outline how to apply these customizations:

**1.** Define a control template in your XAML file. This template will specify the layout and appearance of the RadScheduler header.

```xml
<ContentPage.Resources>
    <ResourceDictionary>
        <Style TargetType="Label" x:Key="HeaderLabelStyle">
            <Setter Property="TextColor" Value="#674BB2" />
            <Setter Property="FontAttributes" Value="Bold" />
            <Setter Property="HorizontalOptions" Value="Center"/>
        </Style>
        <ControlTemplate x:Key="CustomSchedulerMobileTemplate">
            <Grid RowDefinitions="Auto, *">
                <telerik:RadBorder Style="{TemplateBinding ActualHeaderBorderStyle}">
                    <Grid ColumnDefinitions="*, Auto">
                        <Label Style="{TemplateBinding ActualHeaderLabelStyle}" />
                        <Button Grid.Column="1"
                                Style="{TemplateBinding ActualTodayButtonStyle}"
                                IsVisible="{TemplateBinding IsTodayButtonVisible}"
                                Command="{TemplateBinding TodayCommand}" />
                    </Grid>
                </telerik:RadBorder>
                <telerik:RadSchedulerContent x:Name="PART_SchedulerContent"
                                             Grid.Row="1"
                                             IsClippedToBounds="True" />
            </Grid>
        </ControlTemplate>
    </ResourceDictionary>
</ContentPage.Resources>

<telerik:RadScheduler x:Name="scheduler" 
                       HeaderLabelStyle="{StaticResource HeaderLabelStyle}">
    <telerik:RadScheduler.ViewDefinitions>
        <telerik:MonthViewDefinition Title="Month Schedule" 
                               HeaderTextFormat="{}{0:MMM yyyy}" />
    </telerik:RadScheduler.ViewDefinitions>
</telerik:RadScheduler>
```

**2.** Apply the control template to the RadScheduler component in your code-behind, specifically for iOS and Android platforms:

```csharp
public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();

#if ANDROID || IOS
        this.scheduler.ControlTemplate = this.Resources["CustomSchedulerMobileTemplate"] as ControlTemplate;
#endif
    }
}
```

By following these steps, you can customize the RadScheduler header according to your requirements, including removing specific buttons and aligning text.



