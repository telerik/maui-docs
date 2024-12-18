---
title: Customizing Search Panel in DataGrid for MAUI
description: Learn how to customize the search panel in DataGrid for MAUI by removing the options icon.
type: how-to
page_title: Customize DataGrid Search Panel in MAUI by Removing Options Icon
slug: customize-datagrid-search-panel-maui
tags: datagrid, search panel, maui, customization, remove icon
res_type: kb
---

## Environment

| Control | Author | 
| ---- | ---- | 
| DataGrid for MAUI | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

In `RadDataGrid` for MAUI, the search panel includes a default options icon. This article demonstrates how to customize the search panel by removing the options icon while keeping the rest of the search functionality intact.

This knowledge base article also answers the following questions:
- How can I customize the search panel in DataGrid for MAUI?
- Is it possible to remove the options icon from the DataGrid search panel?
- Can I modify the search panel elements in DataGrid for MAUI?

## Solution

To customize the search panel and remove the options icon, you can use the `ControlTemplate` of the `SearchPanel`. The following XAML code shows how to define a `ControlTemplate` that customizes the search panel, focusing on the search entry and close button while excluding the options icon.

```xml
<ContentPage xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
             xmlns:telerikMauiControls="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
             xmlns:local="clr-namespace:YourNamespaceHere"
             x:Class="YourNamespaceHere.MainPage">
    <ContentPage.Resources>
        <ResourceDictionary>
             <Style x:Key="DataGridSearchPanel_EntryToolbarItemView_EntryStyle" TargetType="telerikMauiControls:RadEntry">
                <Setter Property="Placeholder" Value="{telerikMauiControls:Localize DataGrid_Search_SearchEntryPlaceholder}" />
                <Setter Property="ReturnType" Value="Search" />
                <Setter Property="ClearButtonVisibility" Value="WhileEditing" />
                <Setter Property="ReserveSpaceForErrorView" Value="False" />
                <Setter Property="VerticalOptions" Value="Center" />
            </Style>

            <Style x:Key="DataGridSearchPanel_EntryToolbarItemView_EntryStyle_Desktop" TargetType="telerikMauiControls:RadEntry" BasedOn="{StaticResource DataGridSearchPanel_EntryToolbarItemView_EntryStyle}">
                <Setter Property="WidthRequest" Value="200" />
            </Style>
            <Style x:Key="DataGridSearchPanel_EntryToolbarItemView_Style" TargetType="telerikMauiControls:EntryToolbarItemView"
                   >
                <Setter Property="EntryStyle" Value="{OnPlatform Default={StaticResource DataGridSearchPanel_EntryToolbarItemView_EntryStyle}, MacCatalyst={StaticResource DataGridSearchPanel_EntryToolbarItemView_EntryStyle_Desktop}, WinUI={StaticResource DataGridSearchPanel_EntryToolbarItemView_EntryStyle_Desktop}}" />
                <Setter Property="Padding" Value="{OnPlatform Default=0, WinUI=2}" />
                <Setter Property="ContentPadding" Value="{OnPlatform Default=0, WinUI=2, MacCatalyst=2}" />
                <Setter Property="MinimumWidthRequest" Value="{OnPlatform Android=222, iOS=38, WinUI=40, MacCatalyst=20}" />
                <Setter Property="MinimumHeightRequest" Value="{OnPlatform Android=48, iOS=38, WinUI=40, MacCatalyst=20}" />
                <Setter Property="HorizontalOptions" Value="{OnPlatform Default=Fill, MacCatalyst=Start, WinUI=Start}" />
                <Setter Property="VerticalOptions" Value="Center" />
            </Style>


            <Style x:Key="DataGridSearchPanel_CloseButtonToolbarItemView_Style" TargetType="telerikMauiControls:ButtonToolbarItemView" 
                   >
                <Setter Property="HorizontalOptions" Value="End" />
                <Setter Property="VerticalOptions" Value="Center" />
            </Style>
            

            <ControlTemplate x:Key="DataGridSearchPanel_ControlTemplate">
                <telerik:RadToolbar BindingContext="{TemplateBinding DataGrid.SearchSettings}"
                                    BackgroundColor="{OnPlatform Default=#F8F8F8, iOS=#33787880, WinUI=#E2E2E2}"
                                    BorderThickness="1, 1, 1, 0"
                                    ContentPadding="{OnPlatform Android='16, 0', iOS='16, 3', MacCatalyst='12, 4', WinUI='8, 2'}"
                                    OverflowMode="Clip">
                    <telerik:EntryToolbarItem PlacementOptions="ToolStrip"
                                              Text="{Binding IntermediateSearchText}"
                                              telerikMauiControls:EntryExtensions.CompletedCommand="{Binding SearchEntryCompletedCommand}"
                                              Style="{StaticResource DataGridSearchPanel_EntryToolbarItemView_Style}" />
                   
                    <telerik:LabelToolbarItem Text="{Binding ResultsSummary}"
                                              IsVisible="{OnPlatform Android=False, iOS=False}" />
                    <telerik:ButtonToolbarItem PlacementOptions="ToolStrip"
                                               Command="{Binding CloseSearchPanelCommand}"
                                               IsVisible="{Binding IsCloseSearchPanelButtonVisible}"
                                               Style="{StaticResource DataGridSearchPanel_CloseButtonToolbarItemView_Style}">
                        <telerik:LabelToolbarItem.ImageSource>
                            <FontImageSource Glyph="{x:Static telerik:TelerikFont.IconCross}"
                                     FontFamily="{x:Static telerik:TelerikFont.Name}"
                                     Size="16" />
                        </telerik:LabelToolbarItem.ImageSource>
                    </telerik:ButtonToolbarItem>
                </telerik:RadToolbar>
            </ControlTemplate>
        </ResourceDictionary>
    </ContentPage.Resources>
    
    <telerik:RadDataGrid x:Name="dataGrid"
                         ItemsSource="{Binding People}">
        <telerik:RadDataGrid.SearchPanel>
            <telerik:DataGridSearchPanel ControlTemplate="{StaticResource DataGridSearchPanel_ControlTemplate}" />
        </telerik:RadDataGrid.SearchPanel>
        <telerik:RadDataGrid.SearchSettings>
            <telerik:DataGridSearchSettings SearchPanelVisibilityMode="AlwaysVisible" />
        </telerik:RadDataGrid.SearchSettings>
    </telerik:RadDataGrid>
</ContentPage>
```

Replace `"YourNamespaceHere"` with your actual namespace. This custom `ControlTemplate` for the search panel includes only the search entry and the close button, effectively removing the options icon.

## See Also

- [DataGrid Overview](https://docs.telerik.com/devtools/maui/controls/datagrid/overview)
- [Customizing DataGrid Appearance](https://docs.telerik.com/devtools/maui/controls/datagrid/styling)
- [Search in DataGrid](https://docs.telerik.com/devtools/maui/controls/datagrid/features/search)
