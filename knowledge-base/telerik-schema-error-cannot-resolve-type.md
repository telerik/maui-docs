---
title: XamlC error XFC0000: Cannot resolve type "http://schemas.telerik.com/2022/xaml/maui:telerik:control".
description: Cannot resolve type Telerik schema xaml error
type: troubleshooting
page_title: schema error cannot resolve type Telerik schema
slug: telerik-schema-error-cannot-resolve-type
position: 
tags: telerik, schema, maui, error, cannot resolve type schema, combobox, segmented control
res_type: kb
---

## Environment
<table>
	<tbody>
		<tr>
			<td>Product Version</td>
			<td>4.0.0</td>
		</tr>
		<tr>
			<td>Product</td>
			<td>ComboBox for .NET MAUI</td>
		</tr>
	</tbody>
</table>


## Description

This article will giude you for what are the approaches used to workaround the common schema error. In general, the error is not related to the Telerik .NET MAUI controls. It is an issue in .NET MAUI framework when custom controls(controls that are not provided from Microsoft .NET MAUI) are used. The issue is logged here: https://github.com/dotnet/maui/issues/7503

## Steps to Reproduce

Start using a custom controls library and add a common schema namespace. 

## Error Message

XamlC error XFC0000: Cannot resolve type "http://schemas.telerik.com/2022/xaml/maui:telerik:control".

## Solution

You can use one of the following approaches to workaround the behavior: 

**1.** Add a `x:Name` to the control.

For example: 

```XAML
    <telerik:RadComboBox x:Name="combo"/>
```

**2.** Instead of using the schema, add the control's namespace:

```XAML
    <telerikCombo:RadComboBox/>
```

And the namespace:

```XAML
xmlns:telerikCombo="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
```

