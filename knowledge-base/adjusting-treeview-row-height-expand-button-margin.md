---
title: Adjusting TreeView Row Height and Expand Button Margin
description: Learn how to set the row height and adjust the margin of the expand button in the TreeView for UI for .NET MAUI.
type: how-to
page_title: Setting Row Height and Customizing Expand Button Margin in TreeView
meta_title: Setting Row Height and Customizing Expand Button Margin in TreeView
slug: adjusting-treeview-row-height-expand-button-margin
tags: treeview, .net maui, row height, expand button, styling
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.1.0 | Telerik UI for .NET MAUI TreeView | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to limit the row height in the [TreeView](https://www.telerik.com/maui-ui/documentation/controls/treeview/overview) and adjust the margin of the expand button.

This knowledge base article also answers the following questions:
- How to set a definitive row height in TreeView?
- How to customize the margin of the expand button in TreeView?
- How to apply styles to TreeView items and buttons?

## Solution

To set a definitive height for rows and adjust the margin of the expand button in TreeView, apply custom styles using `ItemStyle`. Follow these steps:

1. Define a style for the TreeView item button (`TreeViewItemButton_Style`) to customize properties such as margin, padding, height, and width.

```xaml
<Style x:Key="TreeViewItemButton_Style"
       TargetType="telerik:TreeViewItemButton">
    <Setter Property="BackgroundColor" Value="Transparent" />
    <Setter Property="Margin" Value="5" />
    <Setter Property="WidthRequest" Value="{OnPlatform Android=48, iOS=44, MacCatalyst=24, WinUI=26}" />
    <Setter Property="HeightRequest" Value="{OnPlatform Android=48, iOS=44, MacCatalyst=24, WinUI=26}" />
</Style>
```

2. Create a style for the expand button (`TreeViewItemExpandButton_Style`) based on the button style. Customize the appearance of the expand button.

```xaml
<Style x:Key="TreeViewItemExpandButton_Style"
       TargetType="telerik:TreeViewItemExpandButton"
       BasedOn="{StaticResource TreeViewItemButton_Style}">
    <Setter Property="Text" Value="{x:Static telerik:TelerikFont.IconEmpty}" />
    <Setter Property="VisualStateManager.VisualStateGroups">
        <VisualStateGroupList>
            <VisualStateGroup Name="ExpandStates">
                <VisualState Name="Expanded">
                    <VisualState.Setters>
                        <Setter Property="Text" Value="{x:Static telerik:TelerikFont.IconDownArrow}" />
                    </VisualState.Setters>
                </VisualState>
                <VisualState Name="Collapsed">
                    <VisualState.Setters>
                        <Setter Property="Text" Value="{x:Static telerik:TelerikFont.IconRightArrow}" />
                    </VisualState.Setters>
                </VisualState>
            </VisualStateGroup>
        </VisualStateGroupList>
    </Setter>
</Style>
```

3. Define a style for the TreeView item view (`TreeViewStyle`) to set row height and apply the custom expand button style.

```xaml
<Style x:Key="TreeViewStyle" TargetType="telerik:TreeViewItemView">
    <Setter Property="Margin" Value="10,0" />
    <Setter Property="HeightRequest" Value="60" />
    <Setter Property="ExpandButtonStyle" Value="{StaticResource TreeViewItemExpandButton_Style}" />
</Style>
```

4. Apply the styles to the RadTreeView definition.

```xaml
<telerik:RadTreeView x:Name="treeView" Grid.Row="1"
                     AutomationId="treeView" ItemStyle="{StaticResource TreeViewStyle}"
                     ItemsSource="{Binding TreeData}">
    <telerik:TreeViewDescriptor DisplayMemberPath="Name"
                                ItemsSourcePath="Children"
                                TargetType="{x:Type local:TreeDataItem}" />
    <telerik:RadTreeView.BindingContext>
        <local:MainPageViewModel/>
    </telerik:RadTreeView.BindingContext>
</telerik:RadTreeView>
```

## See Also

- [TreeView Overview](https://www.telerik.com/maui-ui/documentation/controls/treeview/overview)
- [TreeView Styling Documentation](https://www.telerik.com/maui-ui/documentation/controls/treeview/styling/item-style)
