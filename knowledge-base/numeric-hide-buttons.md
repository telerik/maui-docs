---
title: Hiding Numeric buttons
description: Learn how to hide the numeric buttons for increasing and decreasing the numeric value
type: how-to
page_title: Hide the numeric buttons for increasing, decreasing the value
slug: numeric-hide-buttons
position:
published: False
tags: numeric, buttons, hide buttons, .net maui, maui
res_type: kb
---

## Environment

| Version | Product | Author |
| --- | --- | ---- |
| 5.1.0 | Telerik UI for .NET MAUI NumericInput | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |


## Description

This article explains how to hide the numeric input buttons. The buttons are used for increasing/decreasing the value. 


## Solution

You have two options for hiding the buttons.

**1.** Use the `DecreaseButtonStyle` and `IncreaseButtonStyle` and set `IsVisible` property to `False`.

```XAML
<telerik:RadNumericInput DecreaseButtonStyle="{StaticResource button}" IncreaseButtonStyle="{StaticResource button}"/>
```

And the Style defined in the resources:

```XAML
<ResourceDictionary>
    <Style TargetType="telerik:RadButton" x:Key="button">
        <Setter Property="IsVisible" Value="False"/>
    </Style>
</ResourceDictionary>
```

**2.** Use the [ControlTemplate]({%slug numericinput-control-template%}) of the `RadNumericInput` and remove the buttons from the control template.  

