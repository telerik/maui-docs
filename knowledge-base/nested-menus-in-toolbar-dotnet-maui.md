---
title: Creating a Two-Level Hierarchy Menu in Toolbar for .NET MAUI
description: Learn how to implement a two-layer hierarchy menu within the Toolbar component for .NET MAUI using context menus for desktop applications.
type: how-to
page_title: Implementing Nested Menus in Toolbar for .NET MAUI
slug: nested-menus-in-toolbar-dotnet-maui
tags: toolbar, .net maui, context menu, nested menu, hierarchy
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 9.0.0 | Telerik UI for .NET MAUI Toolbar | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

## Description

In desktop applications, creating a two-layer hierarchy menu in the Toolbar component might be necessary to organize actions or options efficiently. The goal is to have a main menu item that, when interacted with, displays a secondary level of menu items, possibly on the right side. 

This knowledge base article also answers the following questions:
- How to add nested menus in Toolbar for .NET MAUI?
- How to use a context menu to create a multi-level menu structure in Toolbar?
- How to implement a drop-down button with nested items in the .NET MAUI Toolbar?

## Solution

To create a two-layer hierarchy menu within the Toolbar component for .NET MAUI, utilize the .NET MAUI Context Menu. This approach involves using a `DropDownButtonToolbarItem` and customizing its content template to include nested `MenuFlyoutSubItem` elements. The context menu provides a native way to implement nested menus, especially suited for desktop applications where it can be triggered with a right-click.

Here is a XAML snippet to define a Toolbar with a drop-down button that opens a nested menu:

```xml
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
                            <Label Text="Menu 1">
                                <FlyoutBase.ContextFlyout>
                                    <MenuFlyout>
                                        <MenuFlyoutItem Text="Item 1"
                                                        Clicked="MenuFlyoutItem_Clicked"
                                                        CommandParameter="Param1" />
                                        <MenuFlyoutSubItem Text="Item 2">
                                            <MenuFlyoutItem Text="Item 21"
                                                            Clicked="MenuFlyoutItem_Clicked_1"
                                                            CommandParameter="Param2" />
                                            <MenuFlyoutItem Text="Item 22"
                                                            Clicked="MenuFlyoutItem_Clicked_2"
                                                            CommandParameter="Param3" />
                                            <MenuFlyoutItem Text="Item 23"
                                                            Clicked="MenuFlyoutItem_Clicked_3"
                                                            CommandParameter="Param4" />
                                        </MenuFlyoutSubItem>
                                    </MenuFlyout>
                                </FlyoutBase.ContextFlyout>
                            </Label>
                            <Label Text="Numbered" />
                            <Label Text="Multilevel" />
                        </VerticalStackLayout>
                    </telerik:DropDownButtonToolbarItemViewContent>
                </ControlTemplate>
            </telerik:DropDownButtonToolbarItem.DropDownContentTemplate>
        </telerik:DropDownButtonToolbarItem>
    </telerik:RadToolbar>
</VerticalStackLayout>
```

This snippet demonstrates the creation of a Toolbar with a drop-down button. The button, when clicked, reveals a context menu with multiple selections, including a nested submenu (`MenuFlyoutSubItem`) for organizing related items. The context menu is triggered on a desktop with a right-click action.

## See Also

- [.NET MAUI Context Menu Documentation](https://learn.microsoft.com/en-us/dotnet/maui/user-interface/context-menu?view=net-maui-9.0)
- [Telerik UI for .NET MAUI Toolbar Documentation](https://docs.telerik.com/devtools/maui/controls/toolbar/overview)
