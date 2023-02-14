---
title: Getting Started
page_title: .NET MAUI SignaturePad Documentation - Getting Started
description: "Review how to get started and add the Telerik SignaturePad for .NET MAUI control. in your application."
position: 1
tags: sing pad, signature, maui, .net maui, sign, signature pad
slug: signaturepad-getting-started
---

# Getting Started with .NET MAUI SignaturePad control

This guide provides the information you need to start using the Telerik UI for .NET MAUI SignaturePad by adding the control to your project.

At the end, you will be able to achieve the following result.

![.NET MAUI SignaturePad Getting Started](images/signaturepad-getting-started.png)

## Prerequisites

Before adding the SignaturePad, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#step-1-set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#step-2-download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#step-3-install-telerik-ui-for-net-maui).

## Define the Control

When your .NET MAUI application is set up, you are ready to add a SignaturePad control to your page.

**1.** Here is the SignaturePad definition in XAML and C#:

<snippet id='signaturepad-getting-started-xaml'/>
<snippet id='signaturepad-getting-started-csharp'/>

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

>important For the SignaturePad Getting Started example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}).

## Additional Resources

- [.NET MAUI SignaturePad product page](https://www.telerik.com/maui-ui/signaturepad)
- [.NET MAUI SignaturePad forum page](https://www.telerik.com/forums/maui?tagId=1978)
- [Telerik .NET MAUI blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Signature Configuration]({% slug signaturepad-configuration%})
- [Events]({% slug signaturepad-events%})
- [Commands]({% slug signaturepad-commands%})
- [Saving Options]({% slug signaturepad-saving-options%})