---
title: Getting Started
page_title: Getting Started with .NET MAUI Button
description: Get started with the Telerik UI for .NET MAUI Button control and add the control to your .NET MAUI project.
position: 1
slug: button-getting-started
---

# Getting Started with the .NET MAUI Button

This guide provides the information you need to start using the Telerik UI for .NET MAUI Button by adding the control to your project.

{% if site.has_cta_panels == true %}
{% include cta-panel-maui-overview.html %}
{% endif %}

This is the default look of the `RadButton` control:

![.NET MAUI Button Default Look](images/button-default-look.png)

## Prerequisites

Before adding the Button, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#step-1-set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#step-2-download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#step-3-install-telerik-ui-for-net-maui).

## Define the Control

**1.** When your .NET MAUI application is set up, you are ready to add a Button control to your page:

<snippet id='button-getting-started-xaml' />

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

> For a runnable example with the Button Getting Started scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **Button > Getting Started**.

## Additional Resources

- [.NET MAUI Button Product Page](https://www.telerik.com/maui-ui/button)
- [.NET MAUI Button Forum Page](https://www.telerik.com/forums/maui?tagId=1764)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Positioning the Content of the Button]({% slug button-configuration %})
- [Setting the Border Thickness & Color of Button]({% slug button-styling %})
- [Creating a Circular Button]({%slug button-create-circle-button%})
