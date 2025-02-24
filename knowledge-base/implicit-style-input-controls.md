---
title: Styling ComboBox, AutoComplete and Entry in Telerik MAUI After Upgrading to Version 8.0.0 or Later
description: Learn how to apply implicit and explicit styles to ComboBox, AutoComplete and Entry controls in Telerik MAUI version 8.0.0 or later.
type: how-to
page_title: How to Style ComboBox, AutoComplete and Entry in Telerik MAUI Version 8.0.0+
slug: style-combobox-autocomplete-entry-implicit-explicit
tags: combobox, styling, telerik, maui, implicit style, explicit style
res_type: kb
---

## Environment

| Versions | Product | Author | 
| --- | --- | ---- | 
| 8.0.0 or Later | Telerik UI for .NET MAUI ComboBox, AutoComplete, Entry | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

This knowledge base article answers the following questions:
- How can I apply implicit style to the `RadComboBox`, `RadAutoComplete` and `RadEntry` in Telerik MAUI after an update to 8.0.0 or a later version?
- How do I style the inner input control (`RadTextInput`) used in the `RadComboBox`, `RadAutoComplete` and `RadEntry` in Telerik MAUI version 8.0.0 or later?

## Solution

This example shows how to apply implicit style to the AutoComplete, ComboBox and Entry, and apply explicit style to the inner input control&mdash;TextInput.

**1.** Define the `RadComboBox`, `RadAutoComplete` and `RadEntry` in XAML:

```XAML
<VerticalStackLayout Padding="10" Spacing="20">
    <telerik:RadAutoComplete x:Name="auto"
                                ItemsSource="{Binding Source}" 
                                TextSearchPath="Name"
                                Placeholder="Search autocomplete"/>

    <telerik:RadEntry x:Name="entry"
                        Placeholder="Search entry" />
        
    <telerik:RadComboBox x:Name="combo" 
                            Placeholder="Search combo"
                            IsEditable="True"
                            DisplayMemberPath="Name"
                            SearchTextPath="Name"
                            ItemsSource="{Binding Source}" />
</VerticalStackLayout>
```

**2.** Define the implicit styles to the page's resources or in a global resource dictionary file:

```XAML
 <Style TargetType="telerik:RadTextInput" x:Key="text">
    <Setter Property="Padding" Value="10,0,0,0" />
</Style>

<Style TargetType="telerik:RadAutoComplete">
    <Setter Property="TextColor" Value="LightGray" />
    <Setter Property="BorderThickness" Value="1" />
    <Setter Property="BorderBrush" Value="#FF404040" />
    <Setter Property="PlaceholderColor" Value="LightGray" />
    <Setter Property="BackgroundColor" Value="#FF454545" />
    <Setter Property="TextInputStyle" Value="{StaticResource text}" />
    <Setter Property="VisualStateManager.VisualStateGroups">
        <VisualStateGroupList>
            <VisualStateGroup Name="CommonStates">
                <VisualState Name="Normal" />
                <VisualState Name="Focused">
                    <VisualState.Setters>
                        <Setter Property="telerik:RadAutoComplete.BorderBrush" Value="#FF99DF8E" />
                        <Setter Property="telerik:RadAutoComplete.BackgroundColor" Value="#FF000000" />
                        <Setter Property="telerik:RadAutoComplete.BorderThickness" Value="1" />
                    </VisualState.Setters>
                </VisualState>
                <VisualState Name="MouseOver">
                    <VisualState.Setters>
                        <Setter Property="telerik:RadAutoComplete.BackgroundColor" Value="#FF000000" />
                        <Setter Property="telerik:RadAutoComplete.BorderBrush" Value="#FF99DF8E" />
                        <Setter Property="telerik:RadAutoComplete.BorderThickness" Value="1" />
                    </VisualState.Setters>
                </VisualState>
                <VisualState Name="PointerOver">
                    <VisualState.Setters>
                        <Setter Property="telerik:RadAutoComplete.BackgroundColor" Value="#FF000000" />
                        <Setter Property="telerik:RadAutoComplete.BorderBrush" Value="#FF99DF8E" />
                        <Setter Property="telerik:RadAutoComplete.BorderThickness" Value="1" />
                    </VisualState.Setters>
                </VisualState>
            </VisualStateGroup>
        </VisualStateGroupList>
    </Setter>
</Style>

<Style TargetType="telerik:RadEntry">
    <Setter Property="TextColor" Value="LightGray" />
    <Setter Property="BorderThickness" Value="1" />
    <Setter Property="MinimumHeightRequest" Value="20" />
    <Setter Property="FontSize" Value="14" />
    <Setter Property="BorderBrush" Value="#FF404040" />
    <Setter Property="PlaceholderColor" Value="LightGray" />
    <Setter Property="BackgroundColor" Value="#FF454545" />
    <Setter Property="VisualStateManager.VisualStateGroups">
        <VisualStateGroupList>
            <VisualStateGroup Name="CommonStates">
                <VisualState Name="Normal" />
                <VisualState Name="Focused">
                    <VisualState.Setters>
                        <Setter Property="telerik:RadEntry.BorderBrush" Value="#FF99DF8E" />
                        <Setter Property="telerik:RadEntry.BackgroundColor" Value="#FF000000" />
                        <Setter Property="telerik:RadEntry.BorderThickness" Value="1" />
                    </VisualState.Setters>
                </VisualState>
                <VisualState Name="MouseOver">
                    <VisualState.Setters>
                        <Setter Property="telerik:RadEntry.BackgroundColor" Value="#FF000000" />
                        <Setter Property="telerik:RadEntry.BorderBrush" Value="#FF99DF8E" />
                        <Setter Property="telerik:RadEntry.BorderThickness" Value="1" />
                    </VisualState.Setters>
                </VisualState>
            </VisualStateGroup>
        </VisualStateGroupList>
    </Setter>
</Style>


<Style TargetType="telerik:RadComboBox">
    <Setter Property="TextColor" Value="LightGray" />
    <Setter Property="BorderThickness" Value="1" />
    <Setter Property="BorderBrush" Value="#FF404040" />
    <Setter Property="PlaceholderColor" Value="LightGray" />
    <Setter Property="BackgroundColor" Value="#FF454545" />
    <Setter Property="TextInputStyle" Value="{StaticResource text}" />
    <Setter Property="VisualStateManager.VisualStateGroups">
        <VisualStateGroupList>
            <VisualStateGroup Name="CommonStates">
                <VisualState Name="Normal" />
                <VisualState Name="Focused">
                    <VisualState.Setters>
                        <Setter Property="telerik:RadComboBox.BorderBrush" Value="#FF99DF8E" />
                        <Setter Property="telerik:RadComboBox.BackgroundColor" Value="#FF000000" />
                        <Setter Property="telerik:RadComboBox.BorderThickness" Value="1" />
                    </VisualState.Setters>
                </VisualState>
                <VisualState Name="MouseOver">
                    <VisualState.Setters>
                        <Setter Property="telerik:RadComboBox.BackgroundColor" Value="#FF000000" />
                        <Setter Property="telerik:RadComboBox.BorderBrush" Value="#FF99DF8E" />
                        <Setter Property="telerik:RadComboBox.BorderThickness" Value="1" />
                    </VisualState.Setters>
                </VisualState>
                <VisualState Name="PointerOver">
                    <VisualState.Setters>
                        <Setter Property="telerik:RadComboBox.BackgroundColor" Value="#FF000000" />
                        <Setter Property="telerik:RadComboBox.BorderBrush" Value="#FF99DF8E" />
                        <Setter Property="telerik:RadComboBox.BorderThickness" Value="1" />
                    </VisualState.Setters>
                </VisualState>
            </VisualStateGroup>
        </VisualStateGroupList>
    </Setter>
</Style>
```

For the `RadTextInput` control&mdash;Define the explicit style through  the `TextInputStyle` property of the `RadAutoComplete` and the `RadComboBox` controls.

## See Also

- [Telerik UI for MAUI ComboBox Documentation]({%slug combobox-overview%})
- [Telerik UI for MAUI AutoComplete Documentation]({%slug autocomplete-overview%})
- [Telerik UI for MAUI Entry Documentation]({%slug entry-overview%})
- [Telerik UI for MAUI TextInput Documentation]({%slug entry-textinput%})

