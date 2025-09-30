---
title: Setting Semantic Properties for Navigation Buttons in Calendar
description: Learn how to set SemanticProperties.Description for navigation buttons in the Calendar control in UI for .NET MAUI to meet accessibility requirements.
type: how-to
page_title: Adding Semantic Properties to Calendar Navigation Buttons for Accessibility
meta_title: Adding Semantic Properties to Calendar Navigation Buttons for Accessibility in UI for .NET MAUI
slug: set-semantic-properties-calendar-navigation-buttons
tags: calendar, navigation-buttons, semanticproperties, accessibility, ui-for-dotnet-maui
res_type: kb
---

## Environment

| Version | Product | Author |
| --- | --- | --- |
| 11.1.0 | Calendar for .NET MAUI | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

I need to set semantic properties, specifically the `SemanticProperties.Description`, for the navigation buttons in the [UI for .NET MAUI Calendar](https://www.telerik.com/maui-ui/documentation/controls/calendar/overview) control to meet accessibility standards.

This knowledge base article also answers the following questions:
- How do I add accessibility descriptions for calendar navigation buttons?
- How can I set SemanticProperties for previous and next navigation buttons in a calendar?
- What is the method to define descriptions for navigation buttons in the .NET MAUI Calendar?

## Solution

To set the `SemanticProperties.Description` for the navigation buttons, use the `NavigateToPreviousViewButtonStyle` and `NavigateToNextViewButtonStyle` properties of the Calendar control. 

1. Define styles for the navigation buttons in XAML.

```xml
<Style TargetType="Button" x:Key="NavigateToPreviousViewButtonStyle">
    <Setter Property="SemanticProperties.Description" Value="Navigate to previous view" />
</Style>
<Style TargetType="Button" x:Key="NavigateToNextViewButtonStyle">
    <Setter Property="SemanticProperties.Description" Value="Navigate to next view" />
</Style>
```

2. Assign the styles to the Calendar control.

```xml
<telerik:RadCalendar x:Name="calendar"
                        NavigateToPreviousViewButtonStyle="{StaticResource NavigateToPreviousViewButtonStyle}"
                        NavigateToNextViewButtonStyle="{StaticResource NavigateToNextViewButtonStyle}" />
```

## See Also

- [Styling the Header of the Calendar in UI for .NET MAUI](https://www.telerik.com/maui-ui/documentation/controls/calendar/styling/header-styling)
- [UI for .NET MAUI Calendar Documentation](https://www.telerik.com/maui-ui/documentation/controls/calendar/overview)
