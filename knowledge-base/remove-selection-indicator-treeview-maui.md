---
title: Removing Selection Indicator from TreeView on Windows
description: Learn how to remove the selection indicator from a TreeView in a .NET MAUI application running on Windows.
type: how-to
page_title: How to Remove the Selection Indicator from TreeView in Windows
slug: remove-selection-indicator-treeview-windows
tags: TreeView, .net maui, windows, treeview, selection, indicator, control template, style
res_type: kb
---

## Environment

| Product | Version | Author |
| --- | --- | --- | 
| TreeView for .NET MAUI | 7.1.0 | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

When using a `RadTreeView` in a .NET MAUI application on Windows, the default behavior includes a selection indicator on items that are selected. This article demonstrates how to remove the selection indicator from TreeView by updating the control template.

This KB article also answers the following questions:
- How can I customize the appearance of selected items in `RadTreeView` on Windows?
- What steps are needed to modify the control template of TreeView?
- How do I apply a custom style to TreeView in .NET MAUI?

## Solution

To remove the selection indicator from `RadTreeView` on Windows, follow these steps:

1. Define a new `ControlTemplate` that omits the selection indicator and other undesired visual elements.
2. Create a `Style` for `TreeViewItemView` that applies this `ControlTemplate`.
3. Apply the `Style` either implicitly within the `ResourceDictionary` or explicitly through the `TreeViewDescriptor.ItemStyle` property.

### Example of Implicit Style

Add the following XAML to your .NET MAUI page to apply the style implicitly:

```xml
<ContentPage.Resources>
    <ResourceDictionary>
        <ControlTemplate x:Key="TreeViewItemView_ControlTemplate_WinUI">
            <telerik:RadBorder BackgroundColor="{TemplateBinding BackgroundColor}"
                               BorderColor="{TemplateBinding BorderColor}"
                               BorderBrush="{TemplateBinding BorderBrush}"
                               BorderThickness="{TemplateBinding BorderThickness}"
                               CornerRadius="{TemplateBinding CornerRadius}">
                <Grid>
                    <telerik:TreeViewItemLayout Indentation="{TemplateBinding Indentation}"
                                                Spacing="{TemplateBinding Spacing}"
                                                Padding="{TemplateBinding ContentPadding}">
                        <ContentPresenter />
                    </telerik:TreeViewItemLayout>
                    <!-- this is the selected indicaotr that is displayed on winui when selection is made -->
                    
                    <!--<telerik:RadBorder IsVisible="{TemplateBinding IsSelected}"
                                        BackgroundColor="{x:Static telerikCore:CoreTelerikStyles.AccentColor}"
                                        HorizontalOptions="Start"
                                        CornerRadius="2"
                                        WidthRequest="3"
                                        ScaleY="0.6" />-->
                </Grid>
            </telerik:RadBorder>
        </ControlTemplate>

        <Style TargetType="telerik:TreeViewItemView">
            <Setter Property="ControlTemplate" Value="{StaticResource TreeViewItemView_ControlTemplate_WinUI}"/>
        </Style>
    </ResourceDictionary>
</ContentPage.Resources>
<telerik:RadTreeView x:Name="treeView"
                     AutomationId="treeView"
                     ItemsSource="{Binding Items}">
    <telerik:TreeViewDescriptor DisplayMemberPath="Name"
                                ItemsSourcePath="Children"
                                TargetType="{x:Type local:Item}" />
    <telerik:RadTreeView.BindingContext>
        <local:ViewModel/>
    </telerik:RadTreeView.BindingContext>
</telerik:RadTreeView>
```

### Using Explicit Style

To use an explicit style, set the above-defined style to the `TreeViewDescriptor.ItemStyle` property. Refer to the [TreeView item style]({%slug treeview-item-style%}) documentation for more details on using explicit styles.