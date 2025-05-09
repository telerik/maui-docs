---
title: Adding Line Breaks to Header Text and Fitting Tabs to Screen in TabView for .NET MAUI
description: Learn how to add line breaks to header text and adjust tab widths to fit all tabs within the screen in TabView for .NET MAUI.
type: how-to
page_title: Adjusting Header Text and Tab Size in TabView for .NET MAUI
slug: tabview-line-break-header-tabs-fit-screen-dotnet-maui
tags: tabview, .net-maui, headertext, linebreak, fit-screen
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 10.1.0 | Telerik UI for .NET MAUI TabView | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

I want to enable line breaks for the header text in the [TabView](https://docs.telerik.com/devtools/maui/controls/tabview/overview) component when the text is lengthy. Additionally, I need all tabs to fit within a single screen when there are multiple tabs.

This knowledge base article also answers the following questions:
- How to make header text wrap in TabView for .NET MAUI?
- How to fit all tabs within the screen in TabView for .NET MAUI?
- How to customize tab headers in TabView for .NET MAUI?

## Solution

To achieve line breaks in the header text and ensure all tabs fit within the screen, follow these steps:

### Step 1: Define a Custom Header Template

Create a `ControlTemplate` that enables line breaks in the header text. Use `LineBreakMode="WordWrap"` in the `Label` element to allow text wrapping.

```xml
<VisualElement.Resources>
    <ControlTemplate x:Key="TabViewHeaderTemplate">
        <Grid local:TabViewUtils.EqualHeaderItemWidth="True" RowDefinitions="Auto, Auto">
            <Image Source="{TemplateBinding ImageSource}" Aspect="Center" />
            <Label Text="{TemplateBinding Text}" Grid.Row="1" LineBreakMode="WordWrap" HorizontalTextAlignment="Center" />
        </Grid>
    </ControlTemplate>
</VisualElement.Resources>
```

### Step 2: Use the Custom Header Template in RadTabView

Apply the custom header template to the TabView and define your tabs.

```xml
<Grid>
    <telerik:RadTabView x:Name="tabView"
                        HeaderItemTemplate="{StaticResource TabViewHeaderTemplate}">
```

### Step 3: Add a Utility Class to Calculate Equal Widths for Tabs

Implement a custom utility class `TabViewUtils` to ensure equal widths for all tabs. The key property here is `EqualHeaderItemWidth`. This class dynamically calculates the width for each tab based on the total width of the TabView and the number of tabs.

Include the following utility class in your application code:



Now, set `local:TabViewUtils.EqualHeaderItemWidth="True"` in the header template to apply equal widths to all tabs.

## See Also

- [TabView Overview](https://docs.telerik.com/devtools/maui/controls/tabview/overview)
