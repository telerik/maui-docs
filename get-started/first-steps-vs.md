---
title: First Steps with .NET MAUI in Visual Studio
page_title: Get Started with Telerik UI for .NET MAUI in Visual Studio
description: "Get started with Telerik UI for .NET MAUI and learn how to install and use the controls by utilizing the Telerik NuGet Server and Visual Studio."
tags: maui, dotnet maui, microsoft maui, telerik maui, nuget, ui for .net maui, macos, install
slug: maui-getting-started
position: 2
previous_url: /maui-getting-started, /get-started/first-steps, /installation/windows/install-msi, /first-steps, /get-started/windows/first-steps-msi, /get-started/windows/first-steps-nuget
---

# First Steps with Telerik UI for .NET MAUI in Visual Studio

In this tutorial, you will enhance an existing .NET MAUI application by adding a Telerik UI for .NET MAUI control. You will achieve this by using Visual Studio for Windows and utilizing the Telerik NuGet source that will let you download and install Telerik controls.

## Prerequisites

* To download the Telerik UI for .NET MAUI packages, you need a [Telerik account](https://www.telerik.com/account/). If you don't have one, you can [create one](https://www.telerik.com/account/) for free.
* To create the app, you need Visual Studio 2022 17.8 or later with installed .NET MAUI workload.

## Step 0: Start Your Free Trial

* If you already have an [active license](https://www.telerik.com/account/your-licenses) for Telerik UI for .NET MAUI, skip this step and continue with [Step 1](#step-1-set-up-your-net-maui-project).
* If you don't have an active license, follow the steps below to activate your free trial:

	1. [Download](https://www.telerik.com/try/ui-for-maui) the Progress Trial Installer and open the EXE file.

	1. Make sure that **Telerik UI for .NET MAUI** is selected and continue with the setup.

	1. Log in with your Telerik account and complete the installation.

	After the successful installation of .NET MAUI, the Progress Trial Installer activates your 30 day free trial.


## Step 1: Set Up Your .NET MAUI Project

In this step, you will create a basic .NET MAUI project as a starting point for your application development:

1. Open Visual Studio and select **Create a new project** in the start window.

1. Select the **.NET MAUI App** template, and click the **Next** button.

	![Telerik UI for .NET MAUI - create new MAUI project in Visual Studio](./images/gs-vs-create-maui-app.png)
	
1. Name your project and select a location.

1. Choose the .NET framework for your project.

1. Wait until Visual Studio restores all dependencies (when done, all exclamation marks in the **Dependencies** tree view item disappear).

1. Click the **Windows Machine** button to build and run the app.

	![Telerik UI for .NET MAUI - create new MAUI project in Visual Studio](./images/gs-vs-build-run.png)

If you encounter any issues creating the basic project, see the complete guide in <a href="https://learn.microsoft.com/en-us/dotnet/maui/get-started/first-app?pivots=devices-windows&view=net-maui-8.0&tabs=vswin" target="_blank">Microsoft's .NET MAUI documentation</a>. 

## Step 2: Add the Telerik NuGet Server

Telerik maintains a NuGet feed with official UI for .NET MAUI releases and service packs. These packages are available for registered users with an active trial or commercial license. Adding the Telerik NuGet server as a source in Visual Studio lets you download and install Telerik packages containing controls and utilities.

To add the Telerik NuGet source to Visual Studio:

1. In Visual Studio go to **Tools** > **NuGet Package Manager** > **Package Manager Settings**.

1. Select **Package Sources** and then click the **+** button to add a new package source.

1. Enter a **Name** for the new package source, for example, `telerik.com`.

1. Add the `https://nuget.telerik.com/v3/index.json` URL as a **Source**. Click **OK**.

1. Whenever Visual Studio displays a dialog to enter credentials for `nuget.telerik.com`, use your Telerik account email and password.

	![Add the Telerik NuGet Feed in Visual Studio](./images/telerik-nuget-feed.png)


## Step 3: Install the Telerik UI for .NET MAUI Controls

1. In Visual Studio and go to **Tools** > **NuGet Package Manager** > **Manage NuGet Packages for Solution...**.

2. Install the Telerik UI for .NET MAUI package:

  1. Select the `telerik.com` **Package source** that you [added earlier](#step-2-add-the-telerik-nuget-server). As this is a private NuGet feed, you must authenticate 
  with your [Telerik account](https://www.telerik.com/account/) user name and password.

  1. Select the **Browse** tab and enter `MAUI` in the search box.

		* If using a trial license, select the `Telerik.UI.for.Maui.Trial` package.
		* If using a commercial license, select the `Telerik.UI.for.Maui` package.
  
  1. Select the checkbox for the target Project, and then click **Install**.

	 ![Add Telerik UI for .NET MAUI package to the project](./images/gs-select-nuget-package.png)

## Step 4: Add the Telerik Namespace and Register the Controls

To use the controls in the Telerik UI for .NET MAUI library, add the Telerik namespace:

1. In the `MainPage.xaml` file, locate the root element at the top. with the already available namespaces.
1. Paste the Telerik namespace below the last already available namespace:

	```
	xmlns:telerikCombo="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
	```

To visualize the Telerik controls, register them in the `MauiProgram.cs` file of your project:

1. In the `MauiProgram.cs` file, add the following using statement:

	```
	using Telerik.Maui.Controls.Compatibility;
	```

1. In the `CreateMauiApp` method, call the `UseTelerik` extension method:

	```
	<!-- Code omitted for brevity -->
	.UseMauiApp<App>()
	.UseTelerik()
	<!-- Code omitted for brevity -->
	```

## Step 5: Add a Telerik UI Component

In this step, you will replace the Button control in Microsoft's template with a Telerik control. The Telerik UI for .NET MAUI [TemplatedButton](https://docs.telerik.com/devtools/maui/controls/templatedbutton/overview) that you will use gives you full control over the Button's content.

To add the TemplatedButton control to the application:

1. Delete the existing Button and its event handler:

	1. In the `MainPage.xaml` file, locate the Button with `x:Name="CounterBtn"` and delete it.
	1. In the `MainPage.xaml.cs` code-behind, locate the `OnCounterClicked` event handler and delete it.

1. In the `MainPage.xaml` file, add the Telerik UI for .NET MAUI TemplatedButton and set its content to a string:

	```
	<telerik:RadTemplatedButton x:Name="templatedButton"
		Content="My TemplatedButton Content" />
	```

After adding the basic TemplatedButton and setting the initial content, you can hit `F5` to confirm that the app is running. In the next steps, you will configure the control by adding some interactivity.

## Step 6: Add Custom Content to the TemplatedButton

In this step, you will edit the code-behind file by adding logic that makes the TemplatedButton interactive: clicking the button will change its content and show a loading indicator for two seconds.

1. In the `MainPage.xaml` file, set the new content of the TemplatedButton:

	* Change the [content](https://docs.telerik.com/devtools/maui/controls/templatedbutton/configuration) inside the button by removing the string and defining a `Grid`, which lets you organize the content in a structured layout.
	* In the `Grid`, add a [BusyIndicator](https://docs.telerik.com/devtools/maui/controls/busyindicator/overview) control and adjust its [styling options](https://docs.telerik.com/devtools/maui/controls/busyindicator/animations).
	* In the `Grid`, add a label control for the loading indicator.

		```
		<telerik:RadTemplatedButton x:Name="templatedButton">
			<telerik:RadTemplatedButton.Content>
				<Grid ColumnDefinitions="Auto, *" HorizontalOptions="Center">
					<telerik:RadBusyIndicator x:Name="busy"
									AnimationContentHeightRequest="16"
									AnimationContentColor="#80CBC4"
									AnimationContentWidthRequest="16"
									AnimationType="Animation4"
									IsVisible="{Binding IsBusy,Source={x:Reference busy}}"
									Margin="0, 0, 10, 0" />
					<Label x:Name="loadingLabel" 
				Grid.Column="1"
				TextColor="{Binding Source={RelativeSource AncestorType={x:Type telerik:RadTemplatedButton}}, Path=TextColor}" 
				Text="Load Content" />
				</Grid>
			</telerik:RadTemplatedButton.Content>
		</telerik:RadTemplatedButton>
		```

1. In the `MainPage.xaml.cs` file, add a new member method within the `MainPage` class. This new method adds the logic that controls the content of the button:

	```
	private async void OnTemplatedButtonClicked(object sender, EventArgs e)
	{
		this.busy.IsBusy = true;
		this.loadingLabel.Text = "Loading Data";
		await Task.Delay(TimeSpan.FromSeconds(2));
		this.busy.IsBusy = false;
		this.loadingLabel.Text = "Data is Loaded";
	}
	```

1. Finally, set the `Clicked` event and add some styles to the TemplatedButton. Use the various [appearance options](https://docs.telerik.com/devtools/maui/controls/templatedbutton/styling) provided by the component, for example, `TextColor`, `Background`, `BorderBrush`, and so on:  

	```
	<telerik:RadTemplatedButton x:Name="templatedButton"
								TextColor="Black"
								Background="#FAFAFA"
								BorderBrush="LightGray"
								BorderThickness="1"
								Clicked="OnTemplatedButtonClicked"
								HorizontalOptions="Center">
		<telerik:RadTemplatedButton.Content>
			<Grid ColumnDefinitions="Auto, *" HorizontalOptions="Center">
				<telerik:RadBusyIndicator x:Name="busy"
											AnimationContentHeightRequest="16"
											AnimationContentColor="#80CBC4"
											AnimationContentWidthRequest="16"
											AnimationType="Animation4"
											IsVisible="{Binding IsBusy,Source={x:Reference busy}}"
											Margin="0, 0, 10, 0" />
				<Label x:Name="loadingLabel" 
						Grid.Column="1"
						TextColor="{Binding Source={RelativeSource AncestorType={x:Type telerik:RadTemplatedButton}}, Path=TextColor}" 
						Text="Load Content" />
			</Grid>
		</telerik:RadTemplatedButton.Content>
	</telerik:RadTemplatedButton>
	```

To run the application, press `F5`. Congratulations, you added created your first app with Telerik UI for .NET MAUI controls!

## Next Steps

* [Telerik UI for .NET MAUI Installation Approaches]({% slug installation-approaches %})
* [Available Product Files and Assemblies]({% slug download-product-files %})
* [Restoring NuGet Packages in Your CI Workflow]({% slug nuget-keys %})

## See Also

* [System Requirements for macOS]({% slug system-requirements-mac %})
* [Telerik Toolbox for .NET MAUI on macOS]({% slug toolbox-support-mac %})
* [Telerik Project Template for VS on macOS]({% slug mac-project-template %})
* [Telerik UI for .NET MAUI Product Page](https://www.telerik.com/maui-ui)
