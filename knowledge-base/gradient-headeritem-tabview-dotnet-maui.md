---
title: Applying Gradient to TabView Header Item for .NET MAUI
description: Learn how to apply a gradient background to the Header Item of the TabView component in .NET MAUI.
type: how-to
page_title: Setting Gradient Background for TabView Header Item in .NET MAUI
slug: gradient-header-item-tabview-dotnet-maui
tags: tabview,.net maui, header item, gradient, tabviewheaderitem
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.0.0 | Telerik UI for .NET MAUI TabView | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

I want to apply a gradient background to the header items of the [TabView]({%slug tabview-overview%}) component in .NET MAUI. The headers' background needs to be styled using a `LinearGradientBrush` while maintaining custom styling for other properties like `FontAttributes` and `TextColor`. 

This knowledge base article also answers the following questions:
- How to set a gradient background for TabView headers in .NET MAUI?
- How to customize TabView `HeaderItemStyle` in .NET MAUI?
- How to use `LinearGradientBrush` in TabView `HeaderItemStyle`?

## Solution

To apply a gradient background to the headers in the TabView component, define a custom `HeaderItemStyle` targeting the `TabViewHeaderItem`. Use the `LinearGradientBrush` to specify the gradient background. Below is an example implementation:

```xml
<telerik:RadTabView x:Name="tabView">
    <telerik:RadTabView.HeaderItemStyle>
        <Style TargetType="telerik:TabViewHeaderItem">
            <!-- Customize font style -->
            <Setter Property="FontAttributes" Value="Italic"/>
            <!-- Customize text color -->
            <Setter Property="TextColor" Value="#99000000" />
            <!-- Apply gradient background -->
            <Setter Property="Background">
                <LinearGradientBrush StartPoint="0,0" EndPoint="1,1">
                    <GradientStop Color="Blue" Offset="0.0"/>
                    <GradientStop Color="Blue" Offset="0.4"/>
                    <GradientStop Color="Red" Offset="0.6"/>
                    <GradientStop Color="Red" Offset="1.0"/>
                </LinearGradientBrush>
            </Setter>
        </Style>
    </telerik:RadTabView.HeaderItemStyle>
    <!-- Define TabView items -->
    <telerik:TabViewItem HeaderText="Home">
        <Label Margin="10" Text="This is the content of the Home tab" />
    </telerik:TabViewItem>
    <telerik:TabViewItem HeaderText="Folder">
        <Label Margin="10" Text="This is the content of the Folder tab" />
    </telerik:TabViewItem>
    <telerik:TabViewItem HeaderText="View">
        <Label Margin="10" Text="This is the content of the View tab" />
    </telerik:TabViewItem>
</telerik:RadTabView>
```

## See Also

- [TabView Documentation]({%slug tabview-overview%})
- [Applying Gradient to TabView Header for .NET MAUI]({%slug gradient-header-tabview-dotnet-maui%})