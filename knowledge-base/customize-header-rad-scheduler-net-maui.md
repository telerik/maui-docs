---
title: Customizing Header Settings in RadScheduler for .NET MAUI
description: Learn how to customize the Telerik UI for .NET MAUI Scheduler header by removing mobile controls, retaining the month text, and centering it.
type: how-to
page_title: How to Customize Header in Telerik RadScheduler for .NET MAUI
slug: customize-header-rad-scheduler-net-maui
tags: scheduler, .net maui, header, customize, alignment, navigation button, visible views button
res_type: kb
---

## Environment

| Version | Product | Platform | Author |
| --- | --- | --- | --- |
| 7.0.0 | Telerik UI for .NET MAUI Scheduler | Android and iOS | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

I need to modify the `RadScheduler` header to better suit my application's UI. How can I achieve the following Telerik UI for .NET MAUI Scheduler customizations?

* Remove the drop-down navigation button located at the top left of the header, which opens the calendar, but retain the month text, such as Jun 2024.
* Center the month text within the header.
* Hide the **Available views** button located at the header's top right.

This KB article also answers the following questions:
- How to remove the navigation button from the RadScheduler header?
- How to center the header text in RadScheduler?
- How to hide the "Available views" button in RadScheduler?

## Solution

To customize the header of the [RadScheduler control]({%slug scheduler-overview%}) for .NET MAUI, use a control template. This example assumes that your app already references Telerik UI for .NET MAUI, calls `UseTelerik()` during app setup, and declares the `telerik` XAML namespace. The template is applied only on Android and iOS.

1. Define a control template in the page's XAML resources. Set the label `Text` with `TemplateBinding` so the template retains the scheduler's month text.

```XAML
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
                        <Label Text="{TemplateBinding HeaderText}"
                               Style="{TemplateBinding ActualHeaderLabelStyle}" />
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

2. Apply the control template in the page's code-behind on Android and iOS:

```C#
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

The template removes the mobile navigation and available-views buttons, retains the month text, centers it, and keeps the **Today** button when it is enabled.

## See Also

- [.NET MAUI Scheduler]({%slug scheduler-overview%})
- [.NET MAUI Scheduler Header Settings]({%slug header-settings%})
- [.NET MAUI Scheduler Header Styling]({%slug scheduler-header-styling%})
