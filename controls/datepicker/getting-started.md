---
title: Getting Started
page_title: .NET MAUI DatePicker Documentation - Getting Started
description: Get started with the Telerik UI for .NET MAUI DatePicker and add the control to your .NET MAUI project.
position: 1
previous_url: /controls/datepicker/datepicker-getting-started
slug: datepicker-getting-started
---

# Getting Started with the .NET MAUI DatePicker

This guide provides the information you need to start using the Telerik UI for .NET MAUI DatePicker by adding the control to your project.

At the end, you will achieve the following result:

![DatePicker Getting Started](images/datepicker_getting_started.png)

## Prerequisites

Before adding the DatePicker, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#step-1-set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#step-2-download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#step-3-install-telerik-ui-for-net-maui).

## Define the Control

**1.** When the your .NET MAUI application is set up, you are ready to add a DatePicker control to your page.

```XAML
<telerik:RadDatePicker x:Name="datePicker" />
```

**2.** Add the following namespace:

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


## Additional Resources

- [.NET MAUI DatePicker Product Page](https://www.telerik.com/maui-ui/datepicker)
- [.NET MAUI DatePicker Forum Page](https://www.telerik.com/forums/maui?tagId=1853)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)


## See Also

- [Formatting the Telerik UI for .NET MAUI DatePicker]({%slug datepicker-formatting%})
- [Setting Date Ranges in the .NET MAUI DatePicker]({%slug datepicker-date-range%})
- [.NET MAUI DatePicker Templates]({%slug datepicker-templates%})
- [.NET MAUI DatePicker Selection]({%slug datepicker-selection%})
- [.NET MAUI DatePicker Styling]({%slug datepicker-styling%})
