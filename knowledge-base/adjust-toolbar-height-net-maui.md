---
title: Adjusting Toolbar Height in .NET MAUI
description: Learn how to customize the height of the Toolbar in .NET MAUI by setting HeightRequest and MinimumHeightRequest.
type: how-to
page_title: How to Control Toolbar Height in a .NET MAUI App
slug: adjust-toolbar-height-net-maui
tags: height, toolbar, .net maui, customization
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 9.0.0 | Telerik UI for .NET MAUI Toolbar | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

## Description

In a scenario where a `RadioButtonToolbarItem` is used within a `RadToolbar`, controlling the toolbar's height might seem challenging, especially when targeting Android, as the minimum height appears to be larger.

This knowledge base article also answers the following questions:

- How can I make the Toolbar in .NET MAUI smaller?
- What is the way to adjust the height of a Toolbar item in .NET MAUI?
- Is it possible to customize the Toolbar appearance for different platforms in .NET MAUI?

## Solution

To reduce the height of the `RadToolbar` and adjust the `RadioButtonToolbarItem` to fit within the altered toolbar height, set the `HeightRequest` and `MinimumHeightRequest` properties of the toolbar and toolbar item, respectively. Additionally, configure other relevant properties to ensure the toolbar item is appropriately styled and positioned within the toolbar.

The following example demonstrates how to configure the `RadToolbar` and a `RadioButtonToolbarItem` to achieve a smaller height:

```xaml
<telerik:RadToolbar x:Name="toolbar" HeightRequest="30">
    <telerik:RadioButtonToolbarItem Text="TEST">
        <telerik:RadioButtonToolbarItem.Style>
            <Style TargetType="telerik:RadioButtonToolbarItemView">
                <Setter Property="DisplayOptions" Value="Text" />
                <Setter Property="VerticalContentOptions" Value="Center" />
                <Setter Property="HorizontalContentOptions" Value="Center" />
                <Setter Property="FontSize" Value="{OnPlatform WinUI=14, Android=12}" />
                <Setter Property="ContentPadding" Value="0" />
                <Setter Property="Margin" Value="0" />
                <Setter Property="Padding" Value="1" />
                <Setter Property="MinimumHeightRequest" Value="16" />
            </Style>
        </telerik:RadioButtonToolbarItem.Style>
    </telerik:RadioButtonToolbarItem>
</telerik:RadToolbar>
```

This configuration results in a `RadToolbar` with a reduced height, where the `RadioButtonToolbarItem` is styled to match the toolbar's dimensions and platform-specific appearance requirements.

## See Also

- [Toolbar Overview](https://docs.telerik.com/devtools/maui/controls/toolbar/overview)
- [Styling the Toolbar](https://docs.telerik.com/devtools/maui/controls/toolbar/styling)
