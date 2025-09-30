---
title: Displaying Current Selection State in Calendar for UI for .NET MAUI
description: Learn how to display the current selection state (day, month, or year) in Calendar for UI for .NET MAUI using the DisplayMode property and a custom converter.
type: how-to
page_title: How to Identify Current Selection State in .NET MAUI Calendar
meta_title: How to Identify Current Selection State in .NET MAUI Calendar
slug: identify-current-selection-state-calendar-net-maui
tags: calendar, ui-for-dotnet-maui, displaymode, converter, semanticproperties, description, headerlabelstyle
res_type: kb
---

## Environment

| Version | Product | Author |
| --- | --- | --- |
| 11.1.0 | Calendar for .NET MAUI | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

I want to determine the current selection state in the Calendar for UI for .NET MAUI, such as day, month, or year, to set a different `SemanticProperties.Description` dynamically based on the selection state.

This knowledge base article also answers the following questions:
- How to bind Calendar's DisplayMode property to update UI elements?
- How to use converters to adjust properties dynamically in .NET MAUI?
- How to apply styles dynamically based on Calendar selection state?

## Solution

To achieve this, bind the `DisplayMode` property of the Calendar to the `SemanticProperties.Description` of the header text using the `HeaderLabelStyle` property. Use a custom converter to transform the `DisplayMode` value into the desired format.

1. Define a custom converter to handle the transformation of the `DisplayMode` value.

```csharp
public class MyConverter : IValueConverter
{
    public object Convert(object value, Type targetType, object parameter, CultureInfo culture)
    {
        return value.ToString(); // Convert the DisplayMode to a string representation.
    }

    public object ConvertBack(object value, Type targetType, object parameter, CultureInfo culture)
    {
        throw new NotImplementedException(); // Not needed for this use case.
    }
}
```
2. Create and apply a style for the header label using the `HeaderLabelStyle` property.
3. Bind the `SemanticProperties.Description` to the Calendar's `DisplayMode` property, applying the custom converter.


```xml
<ContentPage xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
             xmlns:local="clr-namespace:MauiApp7"
             x:Class="MauiApp7.MainPage">

    <ContentPage.Resources>
        <ResourceDictionary>
            <local:MyConverter x:Key="myConverter" />
            <Style TargetType="Label" x:Key="HeaderLabelStyle">
                <Setter Property="TextColor" Value="#8660C5" />
                <Setter Property="FontSize" Value="20" />
                <Setter Property="FontAttributes" Value="Italic" />
                <Setter Property="SemanticProperties.Description" Value="{Binding Source={x:Reference calendar}, Path=DisplayMode, Converter={StaticResource myConverter}}"/>
            </Style>
        </ResourceDictionary>
    </ContentPage.Resources>

    <telerik:RadCalendar x:Name="calendar"
                         HeaderLabelStyle="{StaticResource HeaderLabelStyle}" />
</ContentPage>
```

## See Also

- [Calendar for UI for .NET MAUI Overview](https://www.telerik.com/maui-ui/documentation/controls/calendar/overview)
- [UI for .NET MAUI DisplayMode Property Documentation](https://www.telerik.com/maui-ui/documentation/controls/calendar/display-modes)
