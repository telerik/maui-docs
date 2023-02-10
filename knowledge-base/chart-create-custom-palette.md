---
title: Creating Custom Chart Palettes
page_title: Adding Custom Colors to the Chart - .NET MAUI Knowledge Base
description: Learn how to customize the colors of the Telerik UI for .NET MAUI Chart component.
type: how-to
slug: chart-how-to-create-custom-palette
tags: maui, chart, color, custom, palette
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

How can I use custom colors in the Telerik UI for .NET MAUI Chart?

## Solution

The Chart supports the following default set of colors for displaying its data points:

* `#0078D4`
* `#EA005E`
* `#60CCFE`
* `#0093F9`
* `#00B7C3`
* `#FFB900`
* `#C239B3`
* `#6B69D6`

To modify the default built-in colors, implement a custom palette, as demonstrated in the following scenario:

**1.** Create the needed business model:

<snippet id='categorical-data-model'/>

**2.** Use the sample data for the binding context:

<snippet id='chart-customization-custompalette-viewmodel'/>

**3.** Declare the `RadCartesianChart` in XAML or C#:

<snippet id='chart-customization-custompalette-xaml'/>
<snippet id='chart-customization-custompalette-csharp'/>

The following image shows the end result of the suggested implementation.

![Chart Custom Palette](images/chart-how-to-create-custom-palette.png)

## See Also

- [Categorical Series Combine Mode]({%slug chart-series-combine-mode%})
- [Chart Legend]({%slug chart-features-legend%})
- [How To Create Custom Renderer]({%slug chart-how-to-create-custom-renderer%})
