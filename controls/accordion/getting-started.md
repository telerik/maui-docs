---
title: Getting Started
page_title: .NET MAUI Accordion Documentation - Getting Started
description: Get started with the Telerik UI for .NET MAUI Accordion control and add the control to your .NET MAUI project
position: 1
slug: accordion-getting-started
---

# Getting Started with the .NET MAUI Accordion control

This guide provides the information you need to start using the Telerik UI for .NET MAUI Accordion by adding the control to your project.

At the end, you will be able to achieve the following result.

![Accordion Getting Started](images/accordion-getting-started.png)

## Prerequisites

Before adding the Accordion, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#step-1-set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#step-2-download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#step-3-install-telerik-ui-for-net-maui).

## Define the Control

When your .NET MAUI application is set up, you are ready to add a Accordion control to your page.

**1.** Here is the Accordion definition in XAML and C#:

<snippet id='accordion-getting-started-xaml' />
<snippet id='accordion-getting-started-csharp' />

>important `RadAccordion` provides a read only collection `Items` of type `IList<AccordionItem>`.

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
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

>important For the Accordion Getting Started example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}).

## Additional Resources

- [.NET MAUI Accordion Product Page](https://www.telerik.com/maui-ui/accordion)
- [.NET MAUI Accordion Forum Page](https://www.telerik.com/forums/maui?tagId=1978)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Configuration]({%slug autocomplete-data-binding%})
- [AccordionItem]({%slug accordion-accordion-item%})
