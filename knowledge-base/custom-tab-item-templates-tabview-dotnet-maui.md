---
title: Customize Tab Header Templates of TabView for .NET MAUI
description: Learn how to apply custom templates for each tab item in the header of TabView for .NET MAUI, including using HeaderTemplate and HeaderItemTemplate.
type: how-to
page_title: How to Create Custom Tab Item Templates in TabView Header for .NET MAUI
slug: custom-tab-item-templates-tabview-dotnet-maui
tags: tabview, .net maui, custom template, header template, header item template
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 10.0.0 | Telerik UI for .NET MAUI TabView | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to have a custom template for each tab item in the header of TabView. How can I achieve this?

This knowledge base article also answers the following questions:
- How to customize tab item headers in .NET MAUI TabView?
- Can I add extra UI elements to TabView item headers in .NET MAUI?
- How to apply different styles to TabView item headers in .NET MAUI?

## Solution

To customize each tab item in the header of the [TabView for .NET MAUI](https://docs.telerik.com/devtools/maui/controls/tabview/overview), utilize the `HeaderTemplate` and `HeaderItemTemplate` properties as described in the [Using the HeaderTemplate](#using-the-headertemplate) and [Using the HeaderItemTemplate](#using-the-headeritemtemplate) sections below.
Below are two approaches to achieve this:

### Using the HeaderTemplate

Customize the entire header template, including the items within it, by setting the `HeaderTemplate` property. This approach allows you to override the default header template and insert additional UI elements.

```xml
<telerik:RadTabView x:Name="tabView" IsContentSwipeEnabled="True">
    <telerik:RadTabView.HeaderTemplate>
        <ControlTemplate>
            <telerik:RadBorder BackgroundColor="{TemplateBinding BackgroundColor}"
                   BorderColor="{TemplateBinding BorderColor}"
                   BorderThickness="{TemplateBinding BorderThickness}"
                   CornerRadius="{TemplateBinding CornerRadius}"
                   Padding="{TemplateBinding ContentPadding}">
                <Grid ColumnDefinitions="*, 70">
                    <ContentPresenter Content="{TemplateBinding Content}" />
                    <Label Text="Extra text" Grid.Column="1" />
                </Grid>
            </telerik:RadBorder>
        </ControlTemplate>
    </telerik:RadTabView.HeaderTemplate>
    <!-- Define tab items here -->
</telerik:RadTabView>
```

For styling the header, use the `HeaderStyle` property. Refer to the [Header Styling documentation](https://docs.telerik.com/devtools/maui/controls/tabview/styling/header-styling) for more details.

### Using the HeaderItemTemplate

Apply a common template for all header items through the `HeaderItemTemplate` property. This template can include icons and additional UI elements for the header item. Customize the appearance of header items using `HeaderItemStyle`.

```xml
<telerik:RadTabView x:Name="tabView">
    <telerik:RadTabView.HeaderItemStyle>
        <Style TargetType="telerik:TabViewHeaderItem">
            <!-- Style setters here -->
        </Style>
    </telerik:RadTabView.HeaderItemStyle>
    <telerik:RadTabView.HeaderItemTemplate>
        <ControlTemplate>
            <HorizontalStackLayout>
                <telerik:RadBorder BackgroundColor="{TemplateBinding BackgroundColor}"
                                   BorderColor="{TemplateBinding BorderColor}"
                                   BorderThickness="{TemplateBinding BorderThickness}"
                                   CornerRadius="{TemplateBinding CornerRadius}"
                                   Padding="0"
                                   HeightRequest="55">
                    <HorizontalStackLayout BackgroundColor="LightCyan">
                        <Label Text="{TemplateBinding Text}" HeightRequest="50"/>
                        <Image Source="{TemplateBinding ImageSource}" BackgroundColor="LightGray" />
                        <!-- Additional UI elements here -->
                    </HorizontalStackLayout>
                </telerik:RadBorder>
            </HorizontalStackLayout>
        </ControlTemplate>
    </telerik:RadTabView.HeaderItemTemplate>
    <!-- Define tab items here -->
</telerik:RadTabView>
```

For advanced styling options, including applying style selectors, refer to the [HeaderItemStyleSelector documentation](https://docs.telerik.com/devtools/maui/controls/tabview/styling/header-itemstyle-selector).

## See Also

- [TabView Overview](https://docs.telerik.com/devtools/maui/controls/tabview/overview)
- [Header Styling in TabView](https://docs.telerik.com/devtools/maui/controls/tabview/styling/header-styling)
- [Header Item Styling in TabView](https://docs.telerik.com/devtools/maui/controls/tabview/styling/header-item-styling)
