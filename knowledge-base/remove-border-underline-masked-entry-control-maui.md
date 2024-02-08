---
title: How to Remove Border/Underline in the RadNumericMaskedEntry Control
description: This article provides instructions on how to remove the border or underline in the MaskedEntry control in a .NET MAUI project.
type: how-to
page_title: Removing Border/Underline in MaskedEntry Control for .NET MAUI
slug: remove-border-underline-masked-entry-control-maui
tags: radnumericmaskedentry, control, border, masked control, entry control, underline, .net maui
res_type: kb
---
## Environment
| Version | Product | Author | 
| --- | --- | ---- | 
| 6.7.0 | Telerik UI for .NET MAUI MaskedEntry | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

## Description
I want to remove the border or underline in the RadNumericMaskedEntry control in my .NET MAUI project. How can I achieve this?

## Solution
To remove the border or underline in the RadNumericMaskedEntry control, you can follow one of the following approaches:

### Approach 1: Override the Default Control Template
1. Set the `ControlTemplate` property of the RadNumericMaskedEntry control to a custom control template. For example:
```
<telerik:RadNumericMaskedEntry ControlTemplate="{StaticResource MaskedEntry_ControlTemplate}" />
```
2. Define the custom control template in your resources. Here is an example:
```
<ControlTemplate x:Key="MaskedEntry_ControlTemplate">
    <telerikMauiControls:RadEntry FocusedBorderBrush="Transparent" />
</ControlTemplate>
```

### Approach 2: Use Implicit Style for RadEntry
1. Define an implicit style for the RadEntry control in your resources. For example:
```
<Style TargetType="telerik:RadEntry">
    <Setter Property="FocusedBorderBrush" Value="Transparent" />
</Style>
```
2. Define the RadNumericMaskedEntry control:
```
<telerik:RadNumericMaskedEntry />
```

Please note that in both approaches, the `FocusedBorderBrush` property is set to "Transparent" to remove the border or underline. You can customize the color as needed.
