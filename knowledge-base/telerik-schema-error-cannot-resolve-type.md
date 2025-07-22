---
title: Schema Error Telerik Type cannot be Resolved
page_title: Common schema Error Occurs When Using MS .NET MAUI Framework - .NET MAUI Knowledge Base
description: "Learn how to resolve the common schema error stating XamlC error XFC0000: Cannot resolve type schemas.telerik.com/2022/xaml/maui:telerik:control"
type: troubleshooting
slug: telerik-schema-error-cannot-resolve-type
previous_url: /troubleshooting/app-cannot-build-without-name
tags: telerik, schema, maui, error, cannot resolve type schema, combobox, segmented control
res_type: kb
---

## Environment

<table>
	<tbody>
    <tr>
      <td>Product</td>
			<td>Progress® Telerik® UI for .NET MAUI</td>
    </tr>
  	<tr>
  		<td>Product Version</td>
  		<td>4.0.0</td>
  	</tr>
	</tbody>
</table>


## Description

When I try to use the Telerik UI for .NET MAUI ComboBox component, I get the `XamlC error XFC0000: Cannot resolve type "http://schemas.telerik.com/2022/xaml/maui:telerik:control".` How can I handle this issue?

## Steps to Reproduce

Start using a custom controls library and add a common `schema` namespace.

## Error Message

```bash
XamlC error XFC0000: Cannot resolve type "http://schemas.telerik.com/2022/xaml/maui:telerik:control".
```

## Cause

This common `schema` error is not related to the Telerik UI for .NET MAUI controls, but is a [logged issue that stems from the .NET MAUI framework](https://github.com/dotnet/maui/issues/7503) when the customer uses custom controls, that is, controls that are not provided by Microsoft .NET MAUI.

## Solution

To work around this undesired behavior, add a `x:Name` to the control, for example:

```XAML
    <telerik:RadComboBox x:Name="combo"/>
```

An alternative approach is instead of using the schema, to add the namespace of the control:

```XAML
    <telerikCombo:RadComboBox/>
```

Then, add the common `telerik` namespace:

```XAML
xmlns:telerikCombo="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
```
