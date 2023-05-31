---
title: Chart Palette
page_title: Xamarin Chart Documentation | Custom Chart Palette
description: Check our &quot;Custom Chart Palette&quot; documentation article for Telerik Chart for Xamarin control.
position: 1
slug: chart-how-to-create-custom-palette
---

# .NET MAUI Chart Palette

Chart has a default set of colors when data points are displayed. 

The defualt palette colors on WinUI are: 

* `#0078D4`
* `#EA005E`
* `#60CCFE`
* `#0093F9`
* `#00B7C3`
* `#FFB900`
* `#C239B3`
* `#6B69D6`


## Custom Chart Palette

When a user needs to define custom sets of colors, they can take advantage of custom palettes. Here is an example that shows how to achieve this: 

## Example

Here is an example how to create chart with custom palette:

First, create the needed business model:

<snippet id='categorical-data-model'/>

And here is the sample data used as binding context:

<snippet id='chart-customization-custompalette-viewmodel'/>

Finally, declare the RadCartesianChart in XAML or C#:

<snippet id='chart-customization-custompalette-xaml'/>
<snippet id='chart-customization-custompalette-csharp'/>

Here is the result:

![Chart Custom Palette](images/chart-how-to-create-custom-palette.png)

## See Also

- [Categorical Series Combine Mode]({%slug chart-series-combine-mode%})
- [Chart Legend]({%slug chart-features-legend%})
- [How To Create Custom Renderer]({%slug chart-how-to-create-custom-renderer%})