---
title: Getting Started
page_title: .NET MAUI AutoComplete Documentation - Getting Started
description: Get started with the Telerik UI for .NET MAUI AutoComplete control and add the control to your .NET MAUI project
position: 1
slug: autocomplete-getting-started
---

# Getting Started with the .NET MAUI AutoComplete control

This guide provides the information you need to start using the Telerik UI for .NET MAUI AutoComplete by adding the control to your project.

At the end, you will achieve the following result.

![AutoComplete Getting Started](images/autocomplete-getting-started.png)

## Prerequisites

Before adding the AutoComplete, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#step-1-set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#step-2-download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#step-3-install-telerik-ui-for-net-maui).

## Define the Control

When your .NET MAUI application is set up, you are ready to add a AutoComplete control to your page.

**1.** Here is the AutoComplete definition in XAML and C#:

<snippet id='autocomplete-getting-started-xaml' />
<snippet id='autocomplete-getting-started-csharp' />

**2.** Add the items source for the suggestion list:

<snippet id='autocomplete-getting-started-items-source'/>

**3.** Add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**4.** Register the Telerik controls through the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `CreateMauiApp` method of the `MauiProgram.cs` file of your project:

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

>important For the AutoComplete Getting Started example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}).

## Additional Resources

- [.NET MAUI AutoComplete Product Page](https://www.telerik.com/maui-ui/autocomplete)
- [.NET MAUI AutoComplete Forum Page](https://www.telerik.com/forums/maui?tagId=1978)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Data Binding]({%slug autocomplete-data-binding%})
- [Configuration]({%slug autocomplete-configuration%})
- [Suggest Mode]({%slug autocomplete-suggest-mode%})
- [Display Text]({%slug autocomplete-display-text-formatter%})
- [Tokens Support]({%slug autocomplete-tokens-support%})
- [Remote Search]({%slug autocomplete-remote-search%})
- [Filtering]({%slug autocomplete-filtering%})
- [Events]({%slug autocomplete-events%})
- [Methods]({%slug autocomplete-methods%})
- [Templates]({%slug autocomplete-custom-templates%})
- [Styling]({%slug autocomplete-styling%})

