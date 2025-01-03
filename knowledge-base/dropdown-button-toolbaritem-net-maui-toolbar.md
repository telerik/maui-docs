---
title: Using DropDownButtonToolbarItem in Toolbar for .NET MAUI
description: Learn how to implement and customize the DropDownButtonToolbarItem in a Toolbar for .NET MAUI application.
type: how-to
page_title: How to Customize DropDownButtonToolbarItem in .NET MAUI Toolbar
slug: dropdown-button-toolbaritem-net-maui-toolbar
tags: toolbar, .net maui, dropdownbuttontoolbaritem, controltemplate, displayoptions
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 9.0.0 | Telerik UI for .NET MAUI Toolbar | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

## Description

Implementing a `DropDownButtonToolbarItem` in the Toolbar for .NET MAUI can involve customizing the dropdown content and ensuring text visibility alongside icons. 

This knowledge base article also answers the following questions:
- How to define a content inside the `DropDownButtonToolbarItem`?
- How to display text and image on a `DropDownButtonToolbarItem`?
- How to customize the display options for items within the Toolbar?

## Solution

To add a content inside the `DropDownButtonToolbarItem`, use the `DropDownContentTemplate` property. This property allows you to define a custom layout for the dropdown content. The target type for the `DropDownContentTemplate` is `DropDownButtonToolbarItemViewContent`.

Here is an example:

```xaml
<ContentPage xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
             x:Class="TelerikMauiApp5.MainPage">

    <VerticalStackLayout>
        <telerik:RadToolbar>
            <telerik:DropDownButtonToolbarItem Text="DropDownButton">
                <telerik:DropDownButtonToolbarItem.ImageSource>
                    <FontImageSource Glyph="{x:Static telerik:TelerikFont.IconBulleting}"
                          FontFamily="{x:Static telerik:TelerikFont.Name}"
                          Size="16" />
                </telerik:DropDownButtonToolbarItem.ImageSource>
                <telerik:DropDownButtonToolbarItem.DropDownContentTemplate>
                    <ControlTemplate>
                        <telerik:DropDownButtonToolbarItemViewContent>
                            <VerticalStackLayout Padding="10">
                                <Label Text="Bulleted" />
                                <Label Text="Numbered" />
                                <Label Text="Multilevel" />
                            </VerticalStackLayout>
                        </telerik:DropDownButtonToolbarItemViewContent>
                    </ControlTemplate>
                </telerik:DropDownButtonToolbarItem.DropDownContentTemplate>
            </telerik:DropDownButtonToolbarItem>
        </telerik:RadToolbar>
    </VerticalStackLayout>
</ContentPage>
```

By default, only images are displayed for the toolbar item. To display both text and images in the toolbar items, you can customize the `DisplayOptions` property for `DropDownButtonToolbarItemView`.

Here is an example:

```xaml
<ContentPage.Resources>
    <ResourceDictionary>
        <Style TargetType="telerik:DropDownButtonToolbarItemView">
            <Setter Property="DisplayOptions" Value="Text,Image" />
        </Style>
    </ResourceDictionary>
</ContentPage.Resources>
```

This customization allows you to enhance the user interface by providing both visual and textual cues for toolbar items.

## See Also

- [Toolbar Overview](https://docs.telerik.com/devtools/maui/controls/toolbar/overview)
- [Toolbar Items Styling](https://docs.telerik.com/devtools/maui/controls/toolbar/items/label#styling)
- [Telerik Font Icons](https://docs.telerik.com/devtools/maui/font-icons/overview)
