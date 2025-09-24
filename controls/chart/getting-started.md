---
title: Getting Started
page_title: .NET MAUI Charts Documentation - Getting Started
description: Get started with the Telerik UI for .NET MAUI Chart and add the control to your .NET MAUI project.
tags: chart, .net maui, ui for .net maui, maui, microsoft,
position: 2
previous_url: /controls/chart/chart-getting-started
slug: chart-getting-started
---

# Getting Started with the .NET MAUI Chart

This guide provides the information you need to start using the Telerik UI for .NET MAUI Chart by adding the control to your project.

At the end, you will achieve the following result.

![Basic RadCartesianChart](images/chart-gettingstarted.png "Basic RadCartesianChart")

## Prerequisites

Before adding the Chart, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#step-1-set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#step-2-download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#step-3-install-telerik-ui-for-net-maui).

## Define the Control

**1.** When your .NET MAUI application is set up, you are ready to add a Chart control to your page.

<snippet id='chart-getting-started-xaml' />

```C#
var chart = new RadCartesianChart
{
	HorizontalAxis = new CategoricalAxis(),
	VerticalAxis = new NumericalAxis(),
	BindingContext = new ViewModel()
};

var series = new BarSeries();

series.SetBinding(ChartSeries.ItemsSourceProperty, new Binding("Data"));

series.ValueBinding = new PropertyNameDataPointBinding { PropertyName = "Value" };
series.CategoryBinding = new PropertyNameDataPointBinding { PropertyName = "Category" };

chart.Series.Add(series);
```

**2.** Add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```
```C#
using Telerik.Maui.Controls.Compatibility.Chart;
```

**3.** Register the Telerik controls through the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `CreateMauiApp` method of the `MauiProgram.cs` file of your project:

```C#
using Telerik.Maui.Controls.Compatibility;

public static class MauiProgram
{
	public static MauiApp CreateMauiApp()
	{
		var builder = MauiApp.CreateBuilder();
		builder
			.UseTelerik()
			.UseMauiApp<App>()
			.ConfigureFonts(fonts =>
			{
				fonts.AddFont("OpenSans-Regular.ttf", "OpenSansRegular");
			});

		return builder.Build();
	}
}           
```


## Visualize Sample Data

**1.** Now that you have added the control to your project, define the business model:

<snippet id='categorical-data-model' />

**2.** Set the ViewModel:

<snippet id='chart-getting-started-viewmodel' />

## Additional Resources

- [.NET MAUI Chart Product Page](https://www.telerik.com/maui-ui/chart)
- [.NET MAUI Chart Forum Page](https://www.telerik.com/forums/maui?tagId=1765)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Cartesian Charts]({% slug chart-types-cartesian-chart %})
- [Pie Charts]({% slug chart-types-pie-chart %})
- [Chart Series]({% slug chart-series-overview %})
- [Chart Behaviors]({% slug chart-behaviors-selection %})
- [Chart Axes]({% slug axes-categorical-axis %})
- [Chart Legend]({% slug chart-features-legend %})