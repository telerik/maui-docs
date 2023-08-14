---
title: Hide MaskedEntry Border (underline)
description: Hide the underline or border around the MaskedEntry.
type: how-to
page_title: Hide MaskedEntry Borders
slug: maskedentry-border-styling
tags: maskedentry, textmaskedentry, numericmaskedentry, regexmaskedentry, ipmaskedentry, emailmaskedentry, border, style, hide, underline
position: 5
ticketid: 1619085
res_type: kb
---

## Environment
<table>
    <tbody>
        <tr>
            <td>Product Version</td>
            <td>6.0.0</td>
        </tr>
        <tr>
            <td>Product</td>
            <td>MaskedEntry for MAUI</td>
        </tr>
    </tbody>
</table>


## Description

This how-to article describes how you can change the appearance of the border around the component for both normal and focused states. This border is responsible for the underline beneath the input area.


## Solution

The `RadMaskedEntry` is built on top of the `RadEntry`. This allows you to manage the appearance of both the border and focused border through the following properties of the internal `RadEntry` object:

- Properties controlling the focused state:
  - `FocusedBorderBrush`
  - `FocusedBorderThickness`
- Properties controlling the unfocused state:
  - `BorderBrush`
  - `BorderThickness`

However, you cannot directy access those properties from the `RadMaskedEntry` control. To achieve this you need to define the MaskedEntry's `ControlTemplate`. This template is of type `RadEntry`, and is where you can set the new border values.

1. Confirm your view is already defining the `telerik` namespace:

    ```XAML
    xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
    ```

2. Define a `ControlTemplate` resource in your view's **Resources** and use the following default MaskedEntry template:

    ```XAML
    <ControlTemplate x:Key="MyMaskedEntry_ControlTemplate">
        <telerik:RadEntry AutomationId="MaskedEntryView"
                            IsValueValid="{Binding IsValueValid, Source={x:RelativeSource AncestorType={Type telerik:RadMaskedEntryBase}}}"
                            ValidationErrorMessage="{Binding ActualValidationErrorMessage, Source={x:RelativeSource AncestorType={Type telerik:RadMaskedEntryBase}}}"
                            IsReadOnly="{Binding IsReadOnly, Source={x:RelativeSource AncestorType={Type telerik:RadMaskedEntryBase}}}"
                            IsEnabled="{Binding IsEnabled, Source={x:RelativeSource AncestorType={Type telerik:RadMaskedEntryBase}}}"
                            Placeholder="{Binding Placeholder, Source={x:RelativeSource AncestorType={Type telerik:RadMaskedEntryBase}}}"
                            FontFamily="{Binding FontFamily, Source={x:RelativeSource AncestorType={Type telerik:RadMaskedEntryBase}}}"
                            FontSize="{Binding FontSize, Source={x:RelativeSource AncestorType={Type telerik:RadMaskedEntryBase}}}"
                            ClearButtonVisibility="{Binding ClearButtonVisibility, Source={x:RelativeSource AncestorType={Type telerik:RadMaskedEntryBase}}}"
                            ClearButtonColor="{Binding ClearButtonColor, Source={x:RelativeSource AncestorType={Type telerik:RadMaskedEntryBase}}}"
                            HoveredClearButtonColor="{Binding HoveredClearButtonColor, Source={x:RelativeSource AncestorType={Type telerik:RadMaskedEntryBase}}}"
                            PressedClearButtonColor="{Binding PressedClearButtonColor, Source={x:RelativeSource AncestorType={Type telerik:RadMaskedEntryBase}}}"
                            BackgroundColor="{Binding EntryBackgroundColor, Source={x:RelativeSource AncestorType={Type telerik:RadMaskedEntryBase}}}"
                            CornerRadius="{Binding EntryCornerRadius, Source={x:RelativeSource AncestorType={Type telerik:RadMaskedEntryBase}}}"
                            TextColor="{Binding TextColor, Source={x:RelativeSource AncestorType={Type telerik:RadMaskedEntryBase}}}"
                            Keyboard="{Binding Keyboard, Source={x:RelativeSource AncestorType={Type telerik:RadMaskedEntryBase}}}"/>
    </ControlTemplate>
    ```

3. Update the ControlTemplate using any desired combination of the aforementioned properties to adjust the appearance of the border. the following example uses all four (see last 4 properties):

    ```XAML
    <ControlTemplate x:Key="MyMaskedEntry_ControlTemplate">
        <telerik:RadEntry AutomationId="MaskedEntryView"
                            IsValueValid="{Binding IsValueValid, Source={x:RelativeSource AncestorType={Type telerik:RadMaskedEntryBase}}}"
                            ValidationErrorMessage="{Binding ActualValidationErrorMessage, Source={x:RelativeSource AncestorType={Type telerik:RadMaskedEntryBase}}}"
                            IsReadOnly="{Binding IsReadOnly, Source={x:RelativeSource AncestorType={Type telerik:RadMaskedEntryBase}}}"
                            IsEnabled="{Binding IsEnabled, Source={x:RelativeSource AncestorType={Type telerik:RadMaskedEntryBase}}}"
                            Placeholder="{Binding Placeholder, Source={x:RelativeSource AncestorType={Type telerik:RadMaskedEntryBase}}}"
                            FontFamily="{Binding FontFamily, Source={x:RelativeSource AncestorType={Type telerik:RadMaskedEntryBase}}}"
                            FontSize="{Binding FontSize, Source={x:RelativeSource AncestorType={Type telerik:RadMaskedEntryBase}}}"
                            ClearButtonVisibility="{Binding ClearButtonVisibility, Source={x:RelativeSource AncestorType={Type telerik:RadMaskedEntryBase}}}"
                            ClearButtonColor="{Binding ClearButtonColor, Source={x:RelativeSource AncestorType={Type telerik:RadMaskedEntryBase}}}"
                            HoveredClearButtonColor="{Binding HoveredClearButtonColor, Source={x:RelativeSource AncestorType={Type telerik:RadMaskedEntryBase}}}"
                            PressedClearButtonColor="{Binding PressedClearButtonColor, Source={x:RelativeSource AncestorType={Type telerik:RadMaskedEntryBase}}}"
                            BackgroundColor="{Binding EntryBackgroundColor, Source={x:RelativeSource AncestorType={Type telerik:RadMaskedEntryBase}}}"
                            CornerRadius="{Binding EntryCornerRadius, Source={x:RelativeSource AncestorType={Type telerik:RadMaskedEntryBase}}}"
                            TextColor="{Binding TextColor, Source={x:RelativeSource AncestorType={Type telerik:RadMaskedEntryBase}}}"
                            Keyboard="{Binding Keyboard, Source={x:RelativeSource AncestorType={Type telerik:RadMaskedEntryBase}}}"
                            FocusedBorderBrush="Transparent"
                            FocusedBorderThickness="0,0,0,0" 
                            BorderBrush="Transparent"
                            BorderThickness="0,0,0,0"/>
    </ControlTemplate>
    ```

4. Set your MaskedEntry's `ControlTemplate` property with your new resource's key:

    ```XAML
    <telerik:RadTextMaskedEntry x:Name="MyMaskedEntry"
                                ControlTemplate="{StaticResource MyMaskedEntry_ControlTemplate}"
                                ... />
    ```
