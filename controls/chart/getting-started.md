---
title: Getting Started
page_title: .NET MAUI Charts Documentation - Getting Started
description: "Get started with the Telerik UI for .NET MAUI Chart and add the control to your .NET MAUI project."
tags: chart, .net maui, ui for .net maui, maui, microsoft,
position: 2
previous_url: /controls/chart/chart-getting-started
slug: chart-getting-started
---

# Getting Started

This guide provides the information you need to start using the Telerik UI for .NET MAUI Chart by adding the control to your project.

At the end, you will be able to achieve the following result.

![Basic RadCartesianChart](images/chart-gettingstarted.png "Basic RadCartesianChart")

## Prerequisites

Before adding the Chart, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#install-telerik-ui-for-net-maui).

## Define the Control

1. When your .NET MAUI application is set up, you are ready to add a Chart control to your page.

 <snippet id='chart-getting-started-xaml' />

1. Add the following namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

1. Register the Telerik controls through the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `CreateMauiApp` method of the `MauiProgram.cs` file of your project:

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

1. Now that you have added the control to your project, define the business model:

 <snippet id='categorical-data-model' />

1. Set the ViewModel:

 <snippet id='chart-getting-started-viewmodel' />

## Additional Resources

- [.NET MAUI Chart product page](https://www.telerik.com/maui-ui/chart)
- [.NET MAUI Chart forum page](https://www.telerik.com/forums/maui?tagId=1765)
- [Telerik .NET MAUI blogs](https://www.telerik.com/blogs/tag/.net-maui)
- [Telerik .NET MAUI roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Cartesian Charts]({% slug chart-types-cartesian-chart %})
- [Pie Charts]({% slug chart-types-pie-chart %})
- [Chart Series]({% slug chart-series-overview %})
- [Chart Behaviors]({% slug chart-behaviors-selection %})
- [Chart Axes]({% slug axes-categorical-axis %})
- [Chart Legend]({% slug chart-features-legend %})