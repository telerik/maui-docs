---
title: Hiding IsLeaf Space in TreeView for UI for .NET MAUI
description: Learn how to hide the expand button in the TreeView for UI for .NET MAUI when an item has no children (IsLeaf).
type: how-to
page_title: Hide Expand Button for Leaf Nodes in TreeView for UI for .NET MAUI
meta_title: Hide Expand Button for Leaf Nodes in TreeView for UI for .NET MAUI
slug: hide-expand-button-leaf-nodes-treeview-net-maui
tags: treeview, ui-for-net-maui, isleaf, expand-button
res_type: kb
---

## Environment

| Version | Product | Author |
| --- | --- | ---- |
| 13.2.0 | Telerik UI for .NET MAUI TreeView | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

I need to hide the expand button (IsLeaf space) in the TreeView for UI for .NET MAUI when a node has no children.

This knowledge base article also answers the following questions:
- How to remove the expand button for leaf nodes in TreeView for UI for .NET MAUI?
- How to customize TreeView expand button visibility in UI for .NET MAUI?
- How to hide the expand button for specific TreeView items?

## Solution

To hide the expand button for tree nodes that do not have children, modify the `ExpandButtonStyle` and configure the `IsVisible` property to `False` for the `Leaf` visual state. Use the example below:

```xml
<ContentPage.Resources>
    <ResourceDictionary>
        <Style x:Key="TreeViewItemButton_Style"
               TargetType="telerik:TreeViewItemButton">
            <Setter Property="BackgroundColor" Value="Transparent" />
            <Setter Property="BorderColor" Value="Transparent" />
            <Setter Property="BorderThickness" Value="0" />
            <Setter Property="BorderWidth" Value="0" />
            <Setter Property="CornerRadius" Value="0" />
            <Setter Property="Padding" Value="0" />
            <Setter Property="WidthRequest" Value="{OnPlatform Android=48, iOS=44, MacCatalyst=24, WinUI=26}" />
            <Setter Property="HeightRequest" Value="{OnPlatform Android=48, iOS=44, MacCatalyst=24, WinUI=26}" />
            <Setter Property="HorizontalOptions" Value="Start" />
            <Setter Property="VerticalOptions" Value="Center" />
            <Setter Property="FontSize" Value="12" />
        </Style>
        <Style x:Key="TreeViewItemExpandButton_Style"
               TargetType="telerik:TreeViewItemExpandButton"
               BasedOn="{StaticResource TreeViewItemButton_Style}">
            <Setter Property="Text" Value="{x:Static telerik:TelerikFont.IconEmpty}" />
            <Setter Property="VisualStateManager.VisualStateGroups">
                <VisualStateGroupList>
                    <VisualStateGroup Name="ExpandStates">
                        <VisualState Name="Leaf">
                            <VisualState.Setters>
                                <Setter Property="IsVisible" Value="False" />
                            </VisualState.Setters>
                        </VisualState>
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
        <Style TargetType="telerik:TreeViewItemView" x:Key="TreeViewItemStyle">
            <Setter Property="BackgroundColor" Value="LightBlue" />
            <Setter Property="ExpandButtonStyle" Value="{StaticResource TreeViewItemExpandButton_Style}" />
        </Style>
    </ResourceDictionary>
</ContentPage.Resources>

<Grid Padding="20" RowDefinitions="*">
    <telerik:RadTreeView x:Name="treeView"
                         ItemsSource="{Binding Items}">
        <telerik:RadTreeView.Descriptors>
            <telerik:TreeViewDescriptor DisplayMemberPath="Name"
                                        ItemsSourcePath="Children"
                                        ItemStyle="{StaticResource TreeViewItemStyle}"
                                        TargetType="{x:Type local:TreeItem}"/>
        </telerik:RadTreeView.Descriptors>
    </telerik:RadTreeView>
</Grid>
```

## See Also

- [TreeView for UI for .NET MAUI Documentation](https://www.telerik.com/maui-ui/documentation/controls/treeview/overview)
- [Styling TreeView Items](https://www.telerik.com/maui-ui/documentation/controls/treeview/styling/item-style)
