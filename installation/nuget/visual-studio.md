---
title: Installing with NuGet in Visual Studio
page_title: Adding the Telerik NuGet Server to Visual Studio
description: Learn how to install the UI for .NET MAUI by using the Telerik NuGet Server with Visual Studio.
tags: maui, dot net maui, microsoft maui, telerik maui, nuget, ui for .net maui controls, windows, install, telerik .net maui, 
slug: nuget-server-vs
position: 1
previous_url: /telerik-nuget-server, /get-started/install-nuget, /installation/install-nuget, /get-started/windows/first-steps-nuget
---

# Installing with NuGet in Visual Studio

To install the Telerik UI for .NET MAUI components, you can use the NuGet packages hosted on the public Telerik NuGet server. This online source lets you download and install various versions of the .NET MAUI controls and enables quick updates with minimal manual intervention.

Before adding the Telerik NuGet server to Visual Studio, make sure you have a:

1. .NET MAUI installed on the machine. For more information on the required steps and system requirements, refer to the <a href="https://docs.microsoft.com/en-us/dotnet/maui/get-started/installation" target="_blank">official Microsoft .NET MAUI documentation</a>.
2. Commercial or a trial license for Telerik .NET MAUI. Note that the Telerik NuGet server requires authentication and checks if you have a valid license.

## Step 1: Add the Telerik NuGet Package Source to Visual Studio

To configure the Telerik NuGet feed in Visual Studio:

1. Open Visual Studio.
1. Go to **Tools > NuGet Package Manager > Package Manager Settings**
1. Select **Package Sources**, and then click the + button.
1. In the **Source** field, enter `https://nuget.telerik.com/v3/index.json`. If you use a locally available NuGet package downloaded from <a href="https://www.telerik.com/account/" target="_blank">your account</a>, add the path to the local package instead of the URL.
1. Click **Update** and then **OK**.

  ![Package Sources field with the checked Telerik NuGet option](../../installation/images/nuget-vs-telerik-server.png)

You have successfully added the Telerik NuGet feed as a Package source.


## Step 2: Install the Telerik UI for .NET MAUI NuGet Package

The next steps describe how to authenticate your local NuGet instance and display the available packages:

1. Create a new .NET MAUI project or open an existing project.
1. Right-click the solution in the **Solution Explorer** window.
1. Select **Manage NuGet Packages for Solution...**
1. Select the Telerik NuGet **Package source** from the drop-down list.
1. Click on the **Browse** tab to see the available packages.
1. Enter your Telerik credentials in the Windows Authentication dialog.
1. In the Visual Studio Package Manager, you will see all packages that are licensed to your user account.
1. Search for the `Telerik.UI.for.Maui` or `Telerik.UI.for.Maui.Trial` package and select it.
1. Choose the projects which require the package.
1. Select the desired version and click **Install**.

![Manage Packages for Solutions dialog with the search field and the Telerik.UI.for.MAUI package](../../installation/images/maui-nuget.png)

## Step 3: Register the Required Handlers

To visualize the [.NET MAUI](https://www.telerik.com/maui-ui) controls, you have to register the required handlers by calling the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method inside the `Configure` method of the `MauiProgram.cs` file of your project.

1. Add the needed `using` settings inside the `MauiProgram.cs` file.

 ```C#
using Telerik.Maui.Controls.Compatibility;
 ```

1. Call the `UseTelerik()` method inside the `MauiProgram.cs` file.

 ```C#
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

## Troubleshooting

See the [NuGet Troubleshooting]({%slug troubleshooting-nuget-feed%}) article for tips about common pitfalls when working with the Telerik NuGet feed.