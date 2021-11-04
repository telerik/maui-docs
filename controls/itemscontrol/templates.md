---
title: Templates
page_title: .NET MAUI ItemsControl Documentation | Templates for .NET MAUI ItemsControl
description: "Customize the visualization of the items in the Telerik UI for .NET MAUI ItemsControl by using the supported items template."
position: 4
tags: .net maui, telerik .net maui, ui for .net maui, microsoft .net maui
slug: templates_itemscontrol
---

# Templates

The ItemsControl provides a template for customizing the appearance of its items.  

You can customize the visualization of the ItemsControl items and place various controls inside the control for more appealing designs by using the **ItemTemplate** property.

The following example demonstrates how to set the items template and uses the `Experience` objects together with the [Telerik UI for .NET MAUI Border]({% slug border-overview %}).

```XAML
<telerikMauiControls:RadItemsControl x:Name="itemsControl"
                                ItemsSource="{Binding Experiences, Mode=TwoWay}">
    <telerikMauiControls:RadItemsControl.BindingContext>
        <local:ViewModel />
    </telerikMauiControls:RadItemsControl.BindingContext>
    <telerikMauiControls:RadItemsControl.ItemTemplate>
        <DataTemplate>
            <telerikMauiControls:RadBorder BorderColor="#DFDFDF"
                                           BorderThickness="0, 0, 0, 1">
                <StackLayout Margin="10"
                        Spacing="5">
                    <Label Text="{Binding Title}"
                            FontSize="14"/>
                    <Label Text="{Binding Company}"
                            TextColor="#99000000"
                            FontSize="12"/>
                </StackLayout>
            </telerikPrimitives:RadBorder>
        </DataTemplate>
    </telerikMauiControls:RadItemsControl.ItemTemplate>
</telerikMauiControls:RadItemsControl>
```

The following image shows the end result.

![](images/itemscontrol-itemtemplate.png)

## See Also

- [Setting the Items Source for the ItemsControl]({% slug itemssource_itemscontrol %})
- [Getting Started with Telerik UI for .NET MAUI ItemsControl]({% slug get_started_itemscontrol %})
