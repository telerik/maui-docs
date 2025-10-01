---
title: Getting Started
page_title: .NET MAUI CollectionView Documentation - Getting Started
description: Get started with the Telerik UI for .NET MAUI CollectionView and add the control to your .NET MAUI project.
position: 2
slug: collectionview-getting-started
---

# Getting Started with the .NET MAUI CollectionView

This guide provides the information you need to start using the Telerik UI for .NET MAUI CollectionView by adding the control to your project.

At the end, you will achieve the following result.

![.NET MAUI CollectionView Getting Started](images/collectionview-getting-started.png)

## Prerequisites

Before adding the CollectionView, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#step-1-set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#step-2-download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#step-3-install-telerik-ui-for-net-maui).

1. [Register the required handlers]({%slug maui-getting-started %}#step-4-register-required-handlers).

## Define the Control

**1.** When your .NET MAUI application is set up, you are ready to add a CollectionView control to your page. The following example shows a sample CollectionView definition populated with sample data:

**2.** Define the `RadCollectionView` in XAML:

<snippet id='collectionview-gettingstarted-xaml'/>
<snippet id='collectionview-getting-started-csharp'/>

**3.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**4.** Create sample `DataModel`:

<snippet id='collectionview-datamodel' />

**5.** Define the `ViewModel` class:

<snippet id='collectionview-viewmodel' />

**6.** Register the Telerik controls through the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `CreateMauiApp` method of the `MauiProgram.cs` file of your project:

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

> For a runnable demo with the CollectionView Getting Started example, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **CollectionView > Getting Started** category.

## Additional Resources

- [.NET MAUI CollectionView Overview]({%slug collectionview-overview%})
- [Data Binding]({%slug collectionview-data-binding%})
- [Grouping]({%slug collectionview-grouping%})
- [Filtering]({%slug collectionview-filtering%})
- [Sorting]({%slug collectionview-sorting%})
- [Selection]({%slug collectionview-selection%})
- [Commands]({%slug collectionview-commands%})
- [Events]({%slug collectionview-events%})

## See Also

- [.NET MAUI CollectionView Product Page](https://www.telerik.com/maui-ui/collectionview)
- [.NET MAUI CollectionView Forum Page](https://www.telerik.com/forums/maui?tagId=1829)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)