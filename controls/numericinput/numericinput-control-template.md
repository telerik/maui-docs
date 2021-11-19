---
title: Control Template
page_title: .NET MAUI NumericInput Documentation | Control Template
description: Check our &quot;Control Template&quot; documentation article for Telerik NumericInput for .NET MAUI
position: 6
slug: numericinput-control-template
---

# Control Template

The visual appearance of the NumericInput is defined through a Control Template. To customize the way the NumericInput looks, you would need to take the default `ControlTemplate` and modify it.

This topic gives an overview of the `ControlTemplate` of the NumericInput control, so you can copy it to your app and make changes. The template consists of **Decrease** and **Increase** buttons, the entry control for entering values as well as the accompanying styles.  

#### The original ControlTemplate

```XAML
<ResourceDictionary>
	<ControlTemplate x:Key="RadNumericInput_ControlTemplate">
	    <Grid ColumnSpacing="10"
	          HeightRequest="{OnPlatform Android='45',iOS='36', UWP='32'}"
	          MinimumHeightRequest="{OnPlatform Android='28',iOS='28', UWP='33'}">
	        <Grid.Resources>
	            <ResourceDictionary>
	                <Style TargetType="telerikNumeric:NumericInputButton" Class="DefaultNumericInputButtonStyle">
	                    <Setter Property="CornerRadius" Value="{OnPlatform iOS='10', UWP='0'}"/>
	                    <Setter Property="BorderColor" Value="{x:Static Application.AccentColor}"/>
	                    <Setter Property="TextColor" Value="{x:Static Application.AccentColor}"/>
	                    <Setter Property="BackgroundColor" Value="Transparent"/>
	                    <Setter Property="BorderThickness" Value="2"/>
	                    <Setter Property="VerticalContentAlignment" Value="Center"/>
	                    <Setter Property="HorizontalContentAlignment" Value="Center"/>
	                    <Setter Property="Padding" Value="0,0,0,0"/>
	                </Style>
	                <Style TargetType="telerikNumeric:NumericInputEntry" Class="DefaultNumericInputEntryStyle">
	                    <Setter Property="HorizontalTextAlignment" Value="Center"/>
	                    <Setter Property="VerticalTextAlignment" Value="Center"/>
	                    <Setter Property="Padding" Value="0,0,0,0"/>
	                    <Setter Property="Keyboard" Value="Numeric"/>
	                    <Setter Property="BorderStyle" Value="{OnPlatform Android='0,0,0,2',iOS='2', UWP='2'}"/>
	                </Style>
	            </ResourceDictionary>
	        </Grid.Resources>
	        <Grid.ColumnDefinitions>
	            <ColumnDefinition Width="58"/>
	            <ColumnDefinition Width="*"/>
	            <ColumnDefinition Width="58"/>
	        </Grid.ColumnDefinitions>
	        <telerikNumeric:NumericInputButton Text="{TemplateBinding DecreaseButtonText}"
	                                  Command="{TemplateBinding DecreaseCommand}"
	                                  StyleClass="DefaultNumericInputButtonStyle"
	                                  common:StyleManager.InheritedStyleClass="{TemplateBinding ActualStyleClass}"
	                                  AutomationId="NumericDecreaseButton"
	                                  AutomationProperties.HelpText="{OnPlatform iOS='NumericDecreaseButton', UWP='NumericDecreaseButton'}"/>

	        <telerikNumeric:NumericInputEntry Grid.Column="1"
	                                 x:Name="PART_Entry"
	                                 StyleClass="DefaultNumericInputEntryStyle"
	                                 Text="{TemplateBinding Value, Mode=OneWay}"
	                                 InputTransparent="{TemplateBinding IsReadOnly}"
	                                 common:StyleManager.InheritedStyleClass="{TemplateBinding ActualStyleClass}"
	                                 AutomationId="NumericEntry"/>

	        <telerikNumeric:NumericInputButton Grid.Column="2"
	                                  Text="{TemplateBinding IncreaseButtonText}"
	                                  Command="{TemplateBinding IncreaseCommand}"
	                                  StyleClass="DefaultNumericInputButtonStyle"
	                                  common:StyleManager.InheritedStyleClass="{TemplateBinding ActualStyleClass}"
	                                  AutomationId="NumericIncreaseButton"
	                                  AutomationProperties.HelpText="{OnPlatform iOS='NumericIncreaseButton', UWP='NumericIncreaseButton'}"/>
	    </Grid>
	</ControlTemplate>
</ResourceDictionary>
```

Add the namespaces:

```XAML
xmlns:common="clr-namespace:Telerik.XamarinForms.Common"
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input"
xmlns:telerikNumeric="clr-namespace:Telerik.XamarinForms.Input.NumericInput"
```

You need to copy the original `ControlTemplate` and its resource dependencies to the Resources section of the page, then you can modify the used colors, sizes, relocate or remove elements (for example, you can align the two buttons after the entry).

>important Any `ControlTemplate` element that is prefixed with `"PART_"` is almost always a required part. Removing such a part will result in the control not working. For example the NumericInputEntry control is named `PART_Entry` and cannot be removed.

Set the `ControlTemplate` to the RadNumericInput:

```XAML
<telerikInput:RadNumericInput x:Name="numericInput" ControlTemplate="{StaticReource RadNumericInput_ControlTemplate}" />
```
