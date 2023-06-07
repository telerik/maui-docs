---
title: Getting Started
page_title: .NET MAUI RichTextEditor Documentation - Getting Started
description: Get started with the Telerik UI for .NET MAUI RichTextEditor and add the control to your .NET MAUI project.
position: 1
slug: richtexteditor-getting-started
---

# Getting Started with the .NET MAUI RichTextEditor

This article will guide you through the steps needed to add a basic **RichTextEditor** control in your application.

This guide provides the information you need to start using the [Telerik UI for .NET MAUI RichTextEditor]({%slug richtexteditor-overview%}) by adding the control to your project.

At the end, you will be able to achieve the following result.

![.NET MAUI RichTextEditor Getting Started](images/rte-gettingstarted.png)

## Prerequisites

Before adding the RichTextEditor, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#step-1-set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#step-2-download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#step-3-install-telerik-ui-for-net-maui).

## Define the Control

When your .NET MAUI application is set up, you are ready to add a RichTextEditor control to your page. The following example shows a sample RichTextEditor definition.

> RadRichTextEditor relies on WebView for rendering HTML content. There are some limitations for placing WebView on the page which are valid for RichTextEditor as well:
>
> - Nesting RadRichTextEditor inside ScrollView control is not supported. RadRichTextEditor provides its own scrolling mechanism.
>
> - When the RadRichTextEditor is placed inside a StackLayout, you would need to set explicitly its WidthRequest and HeightRequest properties, otherwise the control will not render. This is due to the fact that StackLayout usually wants to size itself according to its children, but a WebView (since it does scrolling) wants to size itself to its parent. You can learn more about this in the [.NET MAUI WebView documentation](https://learn.microsoft.com/en-us/dotnet/maui/user-interface/controls/webview?pivots=devices-windows).

>
> You should either use a Grid as a parent container or define explicitly the size of the RichTextEditor control.


**1.** Set up the `RichTextEditor` instance:

<snippet id='richtexteditor-getting-started-xaml' />

In addition to this, you need to add the following namespace:

**2.** Add the `telerik` namespaces:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

## Loading HTML Content

With RichTextEditor users can create and edit HTML content. In some cases you may need to load formatted text in advance - this can be achieved through the *Source* property of the control:

<snippet id='richtexteditor-getting-started' />

This is the result:

![RichTextEditor Getting Started Example](images/richtexteditor-getting-started.png "RichTextEditor Getting Started Example")

Register the Telerik controls through the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `CreateMauiApp` method of the `MauiProgram.cs` file of your project:

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

>important For the RichTextEditor Getting Started example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) RichTextEditor -> Getting Started category.

## Additional Resources

- [.NET MAUI RichTextEditor Product Page](https://www.telerik.com/maui-ui/richtexteditor)
- [.NET MAUI RichTextEditor Forum Page](https://www.telerik.com/forums/maui?tagId=1829)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Commands]({%slug richtexteditor-commands%})
- [Configure the RichTextEditor]({%slug richtexteditor-configuration%})
- [Events]({%slug richtexteditor-events%})
- [Working with images]({%slug richtexteditor-images-overview%})
- [Hyperlinks]({%slug richtexteditor-hyperlink-support%})