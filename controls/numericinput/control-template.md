---
title: Control Template
page_title: .NET MAUI NumericInput Documentation | Control Template
description: Check our &quot;Control Template&quot; documentation article for Telerik NumericInput for .NET MAUI
position: 6
previous_url: /controls/numericinput/numericinput-control-template
slug: numericinput-control-template
---

# Control Template

The visual appearance of the NumericInput is defined through a Control Template. To customize the way the NumericInput looks, you would need to take the default `ControlTemplate` and modify it.

This topic gives an overview of the `ControlTemplate` of the NumericInput control, so you can copy it to your app and make changes. The template consists of **Decrease** and **Increase** buttons, the entry control for entering values as well as the accompanying styles.  

The following example shows the original `ControlTemplate` used by the NumericInput control.

First, add the required namespace:

```XAML
xmlns:telerik="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
```

Within the appropriate resources section, define the base styles and finally the ControlTemplates for each platform.

```XAML
<ResourceDictionary>
    <ControlTemplate x:Key="RadNumericInput_ControlTemplate_WinUI">
        <Grid>
            <telerik:RadBorder x:Name="PART_BorderVisual"
                               BorderThickness="1, 1, 1, 0"
                               BorderColor="#DFDFDF"
                               CornerRadius="4"
                               HeightRequest="32"
                               IsEnabled="{TemplateBinding IsEnabled}"
                               Padding="0, 0, 4, 0">
                <VisualStateManager.VisualStateGroups>
                    <VisualStateGroup x:Name="CommonStates">
                        <VisualState x:Name="Normal"/>
                        <VisualState x:Name="ReadOnly">
                            <VisualState.Setters>
                                <Setter Property="BorderColor" Value="Transparent"/>
                            </VisualState.Setters>
                        </VisualState>
                        <VisualState x:Name="Disabled">
                            <VisualState.Setters>
                                <Setter Property="BorderColor" Value="#DFDFDF"/>
                            </VisualState.Setters>
                        </VisualState>
                    </VisualStateGroup>
                </VisualStateManager.VisualStateGroups>
                <Grid ColumnDefinitions="*, Auto">
                    <telerik:NumericInputEntry x:Name="PART_Entry"
                                               Style="{TemplateBinding ActualEntryStyle}"/>
                    <HorizontalStackLayout Grid.Column="1"
                                           Spacing="0">
                        <telerik:NumericInputButton Style="{TemplateBinding ActualDecreaseButtonStyle}"/>
                        <telerik:NumericInputButton Style="{TemplateBinding ActualIncreaseButtonStyle}"/>
                    </HorizontalStackLayout>
                </Grid>
            </telerik:RadBorder>
            <telerik:RadBorder x:Name="PART_FocusBorderVisual"
                               BorderThickness="0, 0, 0, 1" 
                               CornerRadius="4"
                               IsEnabled="{TemplateBinding IsEnabled}"
                               BorderColor="#696969">
                <VisualStateManager.VisualStateGroups>
                    <VisualStateGroup x:Name="CommonStates">
                        <VisualState x:Name="Normal"/>
                        <VisualState x:Name="Focused">
                            <VisualState.Setters>
                                <Setter Property="BorderColor" Value="{StaticResource PrimaryColor}"/>
                            </VisualState.Setters>
                        </VisualState>
                        <VisualState x:Name="ReadOnly">
                            <VisualState.Setters>
                                <Setter Property="BorderColor" Value="Transparent"/>
                            </VisualState.Setters>
                        </VisualState>
                        <VisualState x:Name="Disabled">
                            <VisualState.Setters>
                                <Setter Property="BorderColor" Value="#DFDFDF"/>
                            </VisualState.Setters>
                        </VisualState>
                    </VisualStateGroup>
                </VisualStateManager.VisualStateGroups>
            </telerik:RadBorder>
        </Grid>
    </ControlTemplate>

    <ControlTemplate x:Key="RadNumericInput_ControlTemplate_Android_iOS">
        <Grid ColumnSpacing="4"
              HeightRequest="{OnPlatform Android='44', iOS='36'}"
              ColumnDefinitions="*, Auto">
            <telerik:NumericInputEntry x:Name="PART_Entry"
                                       Style="{TemplateBinding ActualEntryStyle}"/>
            <telerik:RadBorder Grid.Column="1"
                               CornerRadius="{OnPlatform Android='4', iOS='10'}">
                <HorizontalStackLayout Spacing="0">
                    <telerik:NumericInputButton Style="{TemplateBinding ActualDecreaseButtonStyle}"/>
                    <telerik:NumericInputButton Style="{TemplateBinding ActualIncreaseButtonStyle}"/>
                </HorizontalStackLayout>
            </telerik:RadBorder>
        </Grid>
    </ControlTemplate>

    <ControlTemplate x:Key="RadNumericInput_ControlTemplate_MacCatalyst">
        <Grid ColumnSpacing="3.5"
              HeightRequest="34"
              ColumnDefinitions="*, Auto">
            <telerik:NumericInputEntry x:Name="PART_Entry"
                                       Style="{TemplateBinding ActualEntryStyle}"/>
            <telerik:RadBorder Grid.Column="1"
                               CornerRadius="7"
                               WidthRequest="15"
                               BorderThickness="1"
                               BorderColor="#26000000">
                <Grid RowSpacing="0"
                      RowDefinitions="*, *">
                    <telerik:NumericInputButton Style="{TemplateBinding ActualIncreaseButtonStyle}"/>
                    <telerik:NumericInputButton Grid.Row="1"
                                                Style="{TemplateBinding ActualDecreaseButtonStyle}"/>
                </Grid>
            </telerik:RadBorder>
        </Grid>
    </ControlTemplate>
</ResourceDictionary>
```

You need to copy the original `ControlTemplate` and its resource dependencies to the Resources section of the page, then you can modify the used colors, sizes, relocate or remove elements (for example, you can align the two buttons after the entry).

>important Any `ControlTemplate` element that is prefixed with `"PART_"` is always a **required part**. Removing such a part will result in the control not working. For example the NumericInputEntry control is named `PART_Entry` and cannot be removed.

The following example demonstrates how to set the desired `ControlTemplate` depending on the target platform:

```XAML
<telerik:RadNumericInput x:Name="numericInput">
    <telerik:RadNumericInput.ControlTemplate>
        <OnPlatform x:TypeArguments="ControlTemplate">
            <On Platform="WinUI"
                Value="{StaticResource RadNumericInput_ControlTemplate_WinUI}" />
            <On Platform="MacCatalyst"
                Value="{StaticResource RadNumericInput_ControlTemplate_MacCatalyst}" />
            <On Platform="iOS, Android"
                Value="{StaticResource RadNumericInput_ControlTemplate_Android_iOS}" />
        </OnPlatform>
    </telerik:RadNumericInput.ControlTemplate>
</telerik:RadNumericInput>
```
