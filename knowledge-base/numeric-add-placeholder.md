---
title: Add a Placeholder in NumericInput
description: Define a placeholder in numeric entry
type: how-to
page_title: Style and customize the numeric entry
slug: numeric-add-placeholder
position: 
tags: numeric, entry style, placeholder, .net maui, maui
res_type: kb
---

## Environment

| Version | Product | Author |
| --- | --- | ---- |
| 5.1.0 | Telerik UI for .NET MAUI NumericInput | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |


## Description

This article explains how to style and customize the entry inside the NumericInput control. 

## Solution

The NumericInput control has an `EntryStyle` property which is used to style the Entry control. 

For example, if you want to add a placeholder to the control you can achieve this by setting the `Placeholder` to the `EntryStyle`:

```XAML
<telerik:RadNumericInput Grid.Row="3" Value="{x:Null}" EntryStyle="{StaticResource entry}">
```

And the entry style defined in the resources: 

```XAML
<Style TargetType="telerik:RadEntry" x:Key="entry">
    <Setter Property="Placeholder" Value="hello"/>
 </Style>
```

In addition you can customize the inner entry by using the [ControlTemplate]({%slug numericinput-control-template%}) of the `RadNumericInput`.
