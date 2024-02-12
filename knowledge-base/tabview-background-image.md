---
title: TabView with Background Image
description: Transparency in TabView to display background image
type: how-to
page_title: TabView with transparent background
slug: tabview-background-image
position: 
tags: 
ticketid: 1613132
res_type: kb
---

## Environment
| Version | Product | Author | 
| --- | --- | ---- | 
| 5.1.0 | Telerik UI for .NET MAUI TabView | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

## Description

This article shows how to add a transparency in the TabView to display the background image.

## Solution

You have to add styles for the TabView Header, HeaderItem and Content. 

```XAML
<ContentPage xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
             x:Class="MauiApp9.MainPage"
             BackgroundImageSource="dotnet_bot.png">

    <ContentPage.Resources>
        <ResourceDictionary>
            <Style TargetType="telerik:TabViewHeaderItem" x:Key="headerStyle">
                <Setter Property="BackgroundColor" Value="Transparent"/>
            </Style>

            <Style TargetType="telerik:TabViewContent" x:Key="content">
                <Setter Property="BackgroundColor" Value="Transparent"/>
            </Style>

            <Style TargetType="telerik:TabViewHeader" x:Key="header" >
                <Setter Property="BackgroundColor" Value="Transparent"/>
            </Style>
        </ResourceDictionary>
    </ContentPage.Resources>

    <telerik:RadTabView HeaderItemStyle="{StaticResource headerStyle}"
                        HeaderStyle="{StaticResource header}"
                        ContentStyle="{StaticResource content}" x:Name="tabView" AutomationId="tabView" IsContentSwipeEnabled="False">
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
</ContentPage>
```