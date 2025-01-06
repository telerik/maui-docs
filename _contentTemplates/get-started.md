#start-free-trial
* If you already have an [active license](https://www.telerik.com/account/your-licenses) for Telerik UI for .NET MAUI, skip this step and continue with [Step 1](#step-1-set-up-your-net-maui-project).
* If you don't have an active license, follow the steps below to activate your free trial:

    1. [Download](https://www.telerik.com/try/ui-for-maui) the Progress Trial Installer and start the installation.

    1. Make sure that **Telerik UI for .NET MAUI** is selected and continue with the setup.

    1. Log in with your Telerik account and complete the installation.

    After the successful installation of .NET MAUI, the Progress Trial Installer activates your 30 day free trial.
#end

#add-namespace-register-controls
To use the controls in the Telerik UI for .NET MAUI library, add the Telerik namespace:

1. In the `MainPage.xaml` file, locate the root element at the top.
1. Paste the Telerik namespace below the last already available namespace:

	```
	xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
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
#end

#add-telerik-component
In this step, you will replace the Button control in Microsoft's project template with a Telerik control. The Telerik UI for .NET MAUI [TemplatedButton](https://docs.telerik.com/devtools/maui/controls/templatedbutton/overview) that you will use gives you full control over the Button's content.

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
#end

#add-custom-content
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

To run the application, press `F5`. Congratulations, you created your first app with Telerik UI for .NET MAUI controls!
#end
