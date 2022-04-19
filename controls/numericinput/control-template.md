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
xmlns:core="clr-namespace:Telerik.Maui.Core;assembly=Telerik.Maui.Core"
```

Within the appropriate resources section, define the base styles and finally the ControlTemplates for each platform.

```XAML
<ResourceDictionary>
    <Style x:Key="NumericButtonBaseStyle" TargetType="telerik:NumericInputButton">
        <Setter Property="TextColor" Value="Black"/>
        <Setter Property="FontSize" Value="{OnPlatform Default='21', MacCatalyst='7', WinUI='11'}"/>
        <Setter Property="HorizontalContentAlignment" Value="Center"/>
        <Setter Property="VerticalContentAlignment" Value="Center"/>
        <Setter Property="BackgroundColor" Value="{OnPlatform Default='#F8F8F8', MacCatalyst='White', WinUI='#00FFFFFF'}"/>
        <Setter Property="IsEnabled" Value="{TemplateBinding IsEnabled}"/>
        <Setter Property="VisualStateManager.VisualStateGroups">
            <VisualStateGroupList>
                <VisualStateGroup x:Name="CommonStates">
                    <VisualState x:Name="Normal"/>
                    <VisualState x:Name="Disabled">
                        <VisualState.Setters>
                            <Setter Property="TextColor" Value="#61000000"/>
                        </VisualState.Setters>
                    </VisualState>
                </VisualStateGroup>
            </VisualStateGroupList>
        </Setter>
    </Style>

    <Style x:Key="IncreaseButtonBaseStyle" TargetType="telerik:NumericInputButton" BasedOn="{StaticResource NumericButtonBaseStyle}">
        <Setter Property="Text" Value="{TemplateBinding IncreaseButtonText}"/>
        <Setter Property="Command" Value="{TemplateBinding IncreaseCommand}"/>
        <Setter Property="AutomationId" Value="NumericIncreaseButton"/>
    </Style>

    <Style x:Key="DecreaseButtonBaseStyle" TargetType="telerik:NumericInputButton" BasedOn="{StaticResource NumericButtonBaseStyle}">
        <Setter Property="Text" Value="{TemplateBinding DecreaseButtonText}"/>
        <Setter Property="Command" Value="{TemplateBinding DecreaseCommand}"/>
        <Setter Property="AutomationId" Value="NumericDecreaseButton"/>
    </Style>

    <Style x:Key="IncreaseButtonStyle_Catalyst" TargetType="telerik:NumericInputButton" BasedOn="{StaticResource IncreaseButtonBaseStyle}">
        <Setter Property="FontFamily" Value="TelerikFont"/>
        <Setter Property="VerticalContentAlignment" Value="End"/>
        <Setter Property="Padding" Value="0.5, 0, 0, 2.5"/>
    </Style>

    <Style x:Key="DecreaseButtonStyle_Catalyst" TargetType="telerik:NumericInputButton" BasedOn="{StaticResource DecreaseButtonBaseStyle}">
        <Setter Property="FontFamily" Value="TelerikFont"/>
        <Setter Property="VerticalContentAlignment" Value="Start"/>
        <Setter Property="Padding" Value="0.5, 2.5, 0, 0"/>
    </Style>

    <Style x:Key="IncreaseButtonStyle_Android_iOS" TargetType="telerik:NumericInputButton" BasedOn="{StaticResource IncreaseButtonBaseStyle}">
        <Setter Property="MinimumWidthRequest" Value="44"/>
    </Style>

    <Style x:Key="DecreaseButtonStyle_Android_iOS" TargetType="telerik:NumericInputButton" BasedOn="{StaticResource DecreaseButtonBaseStyle}">
        <Setter Property="MinimumWidthRequest" Value="44"/>
    </Style>

    <Style x:Key="IncreaseButtonStyle_WinUI" TargetType="telerik:NumericInputButton" BasedOn="{StaticResource IncreaseButtonBaseStyle}">
        <Setter Property="FontFamily" Value="TelerikFont"/>
        <Setter Property="BorderThickness" Value="0"/>
        <Setter Property="HeightRequest" Value="22"/>
        <Setter Property="WidthRequest" Value="22"/>
        <Setter Property="MinimumWidthRequest" Value="0"/>
        <Setter Property="Padding" Value="5, 0, 5, 0"/>
        <Setter Property="VerticalOptions" Value="Center"/>
    </Style>

    <Style x:Key="DecreaseButtonStyle_WinUI" TargetType="telerik:NumericInputButton" BasedOn="{StaticResource DecreaseButtonBaseStyle}">
        <Setter Property="FontFamily" Value="TelerikFont"/>
        <Setter Property="BorderThickness" Value="0"/>
        <Setter Property="HeightRequest" Value="22"/>
        <Setter Property="WidthRequest" Value="22"/>
        <Setter Property="MinimumWidthRequest" Value="0"/>
        <Setter Property="Padding" Value="5, 0, 5, 0"/>
        <Setter Property="VerticalOptions" Value="Center"/>
    </Style>

    <Style x:Key="NumericEntryBaseStyle" TargetType="telerik:NumericInputEntry">
        <Setter Property="VerticalTextAlignment" Value="Center"/>
        <Setter Property="FontSize" Value="{OnPlatform Android='16', iOS='17', MacCatalyst='15', WinUI='14'}"/>
        <Setter Property="Keyboard" Value="Numeric"/>
        <Setter Property="IsEnabled" Value="{TemplateBinding IsEnabled}"/>
        <Setter Property="BorderBrush" Value="#DFDFDF"/>
        <Setter Property="IsReadOnly" Value="{TemplateBinding IsReadOnly}"/>
        <Setter Property="ClearButtonVisibility" Value="Never"/>
        <Setter Property="AutomationId" Value="NumericEntry"/>
        <Setter Property="VisualStateManager.VisualStateGroups">
            <VisualStateGroupList>
                <VisualStateGroup x:Name="CommonStates">
                    <VisualState x:Name="Normal"/>
                    <VisualState x:Name="ReadOnly">
                        <VisualState.Setters>
                            <Setter Property="BorderThickness" Value="0"/>
                        </VisualState.Setters>
                    </VisualState>
                    <VisualState x:Name="Disabled">
                        <VisualState.Setters>
                            <Setter Property="TextColor" Value="#AAAAAA"/>
                        </VisualState.Setters>
                    </VisualState>
                </VisualStateGroup>
            </VisualStateGroupList>
        </Setter>
    </Style>

    <Style x:Key="NumericEntryStyle_Catalyst" TargetType="telerik:NumericInputEntry" BasedOn="{StaticResource NumericEntryBaseStyle}">
        <Setter Property="CornerRadius" Value="0"/>
    </Style>

    <Style x:Key="NumericEntryStyle_WinUI" TargetType="telerik:NumericInputEntry" BasedOn="{StaticResource NumericEntryBaseStyle}">
        <Setter Property="BorderThickness" Value="0"/>
        <Setter Property="FocusedBorderThickness" Value="0"/>
    </Style>
    
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
                                <Setter Property="BorderColor" Value="{x:Static core:RadMauiCoreHelper.ColorAccent}"/>
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

### See Also

Important Microsoft .NET MAUI Documentation
- [Styles](https://docs.microsoft.com/en-us/dotnet/maui/user-interface/styles/xaml)
- [ControlTemplates](https://docs.microsoft.com/en-us/dotnet/maui/fundamentals/controltemplate)
- [Namespaces](https://docs.microsoft.com/en-us/dotnet/maui/xaml/namespaces/)
- [OnPlatform Markup Extension](https://docs.microsoft.com/en-us/dotnet/maui/xaml/markup-extensions/consume#onplatform-markup-extension)