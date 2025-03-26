---
title: Hiding Numeric buttons
description: Learn how to hide the numeric buttons for increasing and decreasing the numeric value
type: how-to
page_title: Hide the numeric buttons for increasing, decreasing the value
slug: numeric-hide-buttons
position:
tags: numeric, buttons, hide buttons, .net maui, maui
res_type: kb
---

## Environment

| Version | Product | Author |
| --- | --- | ---- |
| 10.0.0 | Telerik UI for .NET MAUI NumericInput | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |


## Description

This article explains how to hide the numeric input buttons. The buttons are used for increasing/decreasing the value. 


## Solution

**1.** Define the .NET MAUI NumericInput control by setting the `DecreaseButtonStyle` (`Style` with target type `RadTemplatedButton`) and the `IncreaseButtonStyle` (`Style` with target type `RadTemplatedButton`) properties:

```XAML
<VerticalStackLayout>
	<telerik:RadNumericInput DecreaseButtonStyle="{StaticResource DecreaseButtonStyle}"
						     IncreaseButtonStyle="{StaticResource IncreaseButtonStyle}" />

</VerticalStackLayout>
```


**2.** To hide the increase and decrease buttons set the `IsVisible` property of the `RadTemplatedButton` to `false`:

```XAML
<ContentPage.Resources>
	<ResourceDictionary>
		<Style x:Key="DecreaseButtonStyle" TargetType="telerik:RadTemplatedButton">
			<Setter Property="IsVisible" Value="False" />
		</Style>

		<Style x:Key="IncreaseButtonStyle" TargetType="telerik:RadTemplatedButton">
			<Setter Property="IsVisible" Value="False" />
		</Style>
	</ResourceDictionary>
</ContentPage.Resources>
```