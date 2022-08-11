---
title: Getting Started
page_title: .NET MAUI TemplatedPicker Documentation - Getting Started
description: "Get started with the Telerik UI for .NET MAUI TemplatedPicker and add the control to your .NET MAUI project."
position: 1
previous_url: /controls/templatedpicker/templatedpicker-getting-started
slug: templatedpicker-getting-started
---

# Getting Started

This guide provides the information you need to start using the Telerik UI for .NET MAUI TemplatedPicker by adding the control to your project.

At the end, you will be able to achieve the following result.

![TemplatedPicker Getting Started](images/templatedpicker_getting_started.png)

## Prerequisites

Before adding the TemplatedPicker, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#install-telerik-ui-for-net-maui).

## Define the Control

The TemplatedPicker exposes a `SelectorTemplate`, which enables you to place any content inside the popup for the user to choose from, and a `DisplayTemplate`, which allows you to present the selected value as required.

1. When your .NET MAUI application is set up, you are ready to add a TemplatedPicker control to your page. The following example demonstrates a custom picker control, which provides the option to choose a color from a set of predefined colors.

 <snippet id='templatedpicker-getting-started-xaml' />
 <snippet id='templatedpicker-getting-started-csharp' />


1. Add the referenced `ColorViewModel`, which holds the collection with the predefined colors:

  <snippet id='templatedpicker-color-viewmodel' />

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
 
## Additional Resources

- [.NET MAUI TemplatedPicker product page](https://www.telerik.com/maui-ui/templatedpicker)
- [.NET MAUI TemplatedPicker forum page](https://www.telerik.com/forums/maui?tagId=1854)
- [Telerik .NET MAUI blogs](https://www.telerik.com/blogs/tag/.net-maui)
- [Telerik .NET MAUI roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Visual Structure]({%slug templatedpicker-visual-structure%})
- [Data Binding]({%slug templatedpicker-data-binding%})
- [Templates]({%slug templatedpicker-templates%})
- [Styling]({%slug templatedpicker-styling%})
