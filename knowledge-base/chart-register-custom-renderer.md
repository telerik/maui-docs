---
title: Registering Custom Chart Renderers When Migrating from Xamarin
page_title: Creating Custom Renderers When Migrating the Chart from Xamarin - .NET MAUI Knowledge Base
description: Learn how to create and register custom renderers in the Telerik UI for .NET MAUI Line Chart component.
type: how-to
slug: chart-how-to-register-custom-renderer
tags: maui, chart, custom, register, renderer
res_type: kb
---

## Environment

<table>
	<tbody>
    <tr>
      <td>Product</td>
      <td>Telerik UI for .NET MAUI Chart</td>
    </tr>
  	<tr>
  		<td>Product Version</td>
  		<td>2.0.0</td>
  	</tr>
	</tbody>
</table>


## Description

How can I create and register a custom renderer for the Telerik UI for .NET MAUI Chart?

## Solution

When a feature is not available in the native control on either of the platforms and is not exposed in `Xamarin.Forms`, you have to create a custom renderer, which will allow you to access the native control and configure it as per your needs.

To achieve the desired scenario, create a class for each platform and register your custom renderer by using the `ExportRenderer` assembly level attribute.

>important GradientBars example demonstrates how to create custom renderer for each platform and it can be found in the Chart/Customization folder of the [SDK Samples Browser application]({%slug developer-focused-examples%}).

### Android Projects

For projects on Android, register the custom renderer for the CartesianChart in the following way:

```C#
[assembly: ExportRenderer(typeof(Telerik.XamarinForms.Chart.RadCartesianChart), typeof(Telerik.XamarinForms.ChartRenderer.Android.CartesianChartRenderer))]
```

The following snippet shows how to register the custom renderer for the PieChart.

```C#
[assembly: ExportRenderer(typeof(Telerik.XamarinForms.Chart.RadPieChart), typeof(Telerik.XamarinForms.ChartRenderer.Android.PieChartRenderer))]
```

### iOS Projects

For projects on iOS, register the custom renderer for the CartesianChart in the following way:

```C#
[assembly: ExportRenderer(typeof(Telerik.XamarinForms.Chart.RadCartesianChart), typeof(Telerik.XamarinForms.ChartRenderer.iOS.CartesianChartRenderer))]
```

The following snippet shows how to register the custom renderer for the PieChart.

```C#
[assembly: ExportRenderer(typeof(Telerik.XamarinForms.Chart.RadPieChart), typeof(Telerik.XamarinForms.ChartRenderer.iOS.PieChartRenderer))]
```

### UWP Projects

For UWP projects, register the custom renderer for the CartesianChart in the following way:

```C#
[assembly: Xamarin.Forms.Platform.UWP.ExportRenderer(typeof(Telerik.XamarinForms.Chart.RadCartesianChart), typeof(Telerik.XamarinForms.ChartRenderer.UWP.CartesianChartRenderer))]
```

The following snippet shows how to register the custom renderer for the PieChart.

```C#
[assembly: Xamarin.Forms.Platform.UWP.ExportRenderer(typeof(Telerik.XamarinForms.Chart.RadPieChart), typeof(Telerik.XamarinForms.ChartRenderer.UWP.PieChartRenderer))]
```

## See Also

- [Categorical Series Combine Mode]({%slug chart-series-combine-mode%})
- [Telerik UI for .NET MAUI Chart Legend]({%slug chart-features-legend%})
