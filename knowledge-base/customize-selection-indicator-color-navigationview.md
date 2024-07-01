---
title: Customizing Selection Indicator Color in NavigationView for .NET MAUI on Windows
description: Learn how to change the selection indicator color of NavigationViewItemView in .NET MAUI NavigationView on Windows.
type: how-to
page_title: How to Customize the Selection Indicator Color in .NET MAUI NavigationView on Windows
slug: customize-selection-indicator-color-navigationview-net-maui
tags: navigationview, .net maui, selection indicator, color, customization
res_type: kb
ticketid: 1656066
---

## Environment

| Product | Version |
| --- | --- |
| Telerik UI for .NET MAUI NavigationView | 7.0.0 |

## Description

When using the [NavigationView](https://docs.telerik.com/devtools/maui/controls/navigationview/overview) in a .NET MAUI application, the selection indicator (a small vertical colored bar) appears in the accent color of the device by default. This article demonstrates how to customize the color of the selection indicator in the NavigationViewItemView.

This KB article also answers the following questions:
- How can I change the NavigationViewItemView indicator color in .NET MAUI?
- What method allows for the customization of the selection indicator in NavigationView?
- Is it possible to override the default accent color of the selection indicator in .NET MAUI NavigationView?

## Solution

To customize the selection indicator color in the `NavigationViewItemView`, override its `ControlTemplate` and modify the `BackgroundColor` of the last `RadBorder` element inside the `NavigationViewItemView_ControlTemplate_WinUI`. Apply an implicit style in your application to achieve this customization.

Below is an example of how to define the implicit style:

```xml
<ResourceDictionary>
	<ControlTemplate x:Key="NavigationViewItemView_ControlTemplate">
		<Grid BackgroundColor="Transparent">
			<telerikMauiControls:RadBorder BackgroundColor="{TemplateBinding BackgroundColor}"
										   Background="{TemplateBinding Background}"
										   BorderColor="{TemplateBinding BorderColor}"
										   BorderBrush="{TemplateBinding BorderBrush}"
										   BorderThickness="{TemplateBinding BorderThickness}"
										   CornerRadius="{TemplateBinding CornerRadius}"
										   Margin="{TemplateBinding ContentPadding}" />
			<Grid ColumnDefinitions="Auto, *"
				  ColumnSpacing="{TemplateBinding Spacing}">
				<Grid WidthRequest="{TemplateBinding LeadingWidth}">
					<Image Source="{TemplateBinding ActualImageSource}"
						   Aspect="{TemplateBinding ImageAspect}"
						   WidthRequest="{TemplateBinding ImageWidth}"
						   HeightRequest="{TemplateBinding ImageHeight}" />
				</Grid>
				<ContentPresenter Grid.Column="1" />
			</Grid>
		</Grid>
	</ControlTemplate>
	<ControlTemplate x:Key="NavigationViewItemView_ControlTemplate_WinUI">
		<Grid BackgroundColor="Transparent">
			<telerikMauiControls:RadBorder BackgroundColor="{TemplateBinding BackgroundColor}"
										   Background="{TemplateBinding Background}"
										   BorderColor="{TemplateBinding BorderColor}"
										   BorderBrush="{TemplateBinding BorderBrush}"
										   BorderThickness="{TemplateBinding BorderThickness}"
										   CornerRadius="{TemplateBinding CornerRadius}"
										   Margin="{TemplateBinding ContentPadding}" />
			<Grid ColumnDefinitions="Auto, *"
				  ColumnSpacing="{TemplateBinding Spacing}">
				<Grid WidthRequest="{TemplateBinding LeadingWidth}">
					<Image Source="{TemplateBinding ActualImageSource}"
						   Aspect="{TemplateBinding ImageAspect}"
						   WidthRequest="{TemplateBinding ImageWidth}"
						   HeightRequest="{TemplateBinding ImageHeight}" />
				</Grid>
				<ContentPresenter Grid.Column="1" />
			</Grid>
			<telerikMauiControls:RadBorder IsVisible="{TemplateBinding IsSelected}"
										   BackgroundColor="Pink"
										   HorizontalOptions="Start"
										   CornerRadius="2"
										   WidthRequest="3"
										   ScaleY="0.5"
										   Margin="{TemplateBinding ContentPadding}" />
		</Grid>
	</ControlTemplate>
	<Style TargetType="telerik:NavigationViewItemView">
		<Setter Property="ControlTemplate" Value="{OnPlatform Default={StaticResource NavigationViewItemView_ControlTemplate}, 
															  WinUI={StaticResource NavigationViewItemView_ControlTemplate_WinUI}}" />
	</Style>
</ResourceDictionary>
```

This style targets the `NavigationViewItemView` and sets the `ControlTemplate` property. Depending on the platform, it uses the appropriate resource (`NavigationViewItemView_ControlTemplate` for default and `NavigationViewItemView_ControlTemplate_WinUI` for Windows).

## Notes

- Remember to define the `ControlTemplate` resources (`NavigationViewItemView_ControlTemplate` and `NavigationViewItemView_ControlTemplate_WinUI`) in your application resources. These templates should include the customization for the selection indicator color.
- The process might require creating a customized control template that replicates the original but with the desired changes to the selection indicator color.

## See Also

- [Telerik UI for .NET MAUI NavigationView Documentation](https://docs.telerik.com/devtools/maui/controls/navigationview/overview)
- [Customizing .NET MAUI Control Templates](https://docs.microsoft.com/en-us/dotnet/maui/fundamentals/control-templates)
