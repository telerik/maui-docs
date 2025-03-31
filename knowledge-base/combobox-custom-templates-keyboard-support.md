---
title: Enabling Keyboard Support with Custom Item Templates in ComboBox for .NET MAUI
description: Learn how to maintain keyboard navigation functionality when using custom item and selected item templates in RadComboBox for .NET MAUI.
type: how-to
page_title: How to Use Custom Templates with Keyboard Support in RadComboBox for .NET MAUI
slug: combobox-custom-templates-keyboard-support
tags: combobox, .net maui, keyboard navigation, custom templates, item template, selected item template
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 10.0.0 | Telerik UI for .NET MAUI ComboBox | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

When applying custom item and selected item templates to a ComboBox, the keyboard support for navigating through items (when the drop-down is open) using the up and down arrow keys does not work. This issue does not occur without the custom templates. 

This knowledge base article also answers the following questions:

- How do I maintain keyboard functionality with custom templates in ComboBox for .NET MAUI?
- What is the correct way to implement custom item templates while preserving keyboard navigation in ComboBox?
- How can I use Visual State Manager with `RadComboBoxItem` to enable keyboard support in .NET MAUI?

## Solution

To ensure that keyboard support works as expected with custom item and selected item templates in ComboBox for .NET MAUI, wrap the content of the templates in a `RadComboBoxItem` and define the necessary visual states, specifically `MouseOver` and `Highlighted`. These states help in maintaining the visual feedback and functionality of keyboard navigation.

Here's an example of how you can define a RadComboBox with custom templates in XAML:

```xml
<telerik:RadComboBox ItemsSource="{Binding Items}" 
                     DisplayMemberPath="Name" 
                     x:Name="combo"
                     Placeholder="Select City"
                     AutomationId="comboBox"
                     SearchMode="StartsWith"
                     OpenOnFocus="False"
                     SearchTextPath="Name">
    <telerik:RadComboBox.ItemTemplate>
        <DataTemplate>
            <telerik:RadComboBoxItem>
                <VisualStateManager.VisualStateGroups>
                    <VisualStateGroup x:Name="CommonStates">
                        <VisualState x:Name="Normal"/>
                        <VisualState x:Name="MouseOver">
                            <VisualState.Setters>
                                <Setter Property="telerik:RadComboBoxItem.BackgroundColor" Value="LightGray"/>
                            </VisualState.Setters>
                        </VisualState>
                        <VisualState Name="Highlighted">
                            <VisualState.Setters>
                                <Setter Property="telerik:RadComboBoxItem.BackgroundColor" Value="LightGray" />
                            </VisualState.Setters>
                        </VisualState>
                    </VisualStateGroup>
                </VisualStateManager.VisualStateGroups>
                <Label Text="{Binding Name}"
                       Padding="8, 7, 0, 7"
                       TextColor="Black"/>
            </telerik:RadComboBoxItem>
        </DataTemplate>
    </telerik:RadComboBox.ItemTemplate>
    <telerik:RadComboBox.SelectedItemTemplate>
        <DataTemplate>
            <telerik:RadComboBoxItem>
                <VisualStateManager.VisualStateGroups>
                    <VisualStateGroup x:Name="CommonStates">
                        <VisualState x:Name="Normal"/>
                        <VisualState x:Name="MouseOver">
                            <VisualState.Setters>
                                <Setter Property="telerik:RadComboBoxItem.BackgroundColor" Value="LightGray"/>
                            </VisualState.Setters>
                        </VisualState>
                        <VisualState Name="Highlighted">
                            <VisualState.Setters>
                                <Setter Property="telerik:RadComboBoxItem.BackgroundColor" Value="LightCoral" />
                            </VisualState.Setters>
                        </VisualState>
                    </VisualStateGroup>
                </VisualStateManager.VisualStateGroups>
                <VerticalStackLayout>
                    <Label Text="{Binding Name}"
                           Padding="8, 7, 0, 7"
                           TextColor="Black"/>
                    <Label Text="{Binding Population}"
                           FontSize="12"
                           Padding="8, 7, 0, 7"/>
                </VerticalStackLayout>
            </telerik:RadComboBoxItem>
        </DataTemplate>
    </telerik:RadComboBox.SelectedItemTemplate>
</telerik:RadComboBox>
```

This implementation wraps the item and selected item templates in a `RadComboBoxItem` and uses the Visual State Manager to define `MouseOver` and `Highlighted` states, ensuring keyboard navigation works seamlessly with custom templates.

## See Also

- [ComboBox Overview](https://docs.telerik.com/devtools/maui/controls/combobox/overview)
