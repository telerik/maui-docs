---
title: Getting Started
page_title: .NET MAUI TemplatedPicker Documentation | Getting Started
description: "Get started with the Telerik UI for .NET MAUI TemplatedPicker and add the control to your .NET MAUI project."
position: 1
slug: templatedpicker-getting-started
---

# Getting Started

This guide provides the information you need to start using the Telerik UI for .NET MAUI Barcode by adding the control to your project.

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

 ```XAML
<telerikInput:RadTemplatedPicker Placeholder="Select a Color">
	<telerikInput:RadTemplatedPicker.BindingContext>
        <local:ColorViewModel />
    </telerikInput:RadTemplatedPicker.BindingContext>
    </telerikInput:RadTemplatedPicker.BindingContext>
	<telerikInput:RadTemplatedPicker.DisplayTemplate>
		<ControlTemplate>
			<Grid BackgroundColor="{TemplateBinding DisplayString}">
				<Grid.GestureRecognizers>
					<TapGestureRecognizer Command="{TemplateBinding ToggleCommand}" />
				</Grid.GestureRecognizers>
				<Label Margin="10, 0"
					   TextColor="Black"
					   VerticalOptions="Center"
					   Text="{TemplateBinding DisplayString}" />
			</Grid>
		</ControlTemplate>
	</telerikInput:RadTemplatedPicker.DisplayTemplate>
	<telerikInput:RadTemplatedPicker.SelectorTemplate>
		<ControlTemplate>
			<CollectionView HeightRequest="240"
							SelectionMode="Single"
							ItemsSource="{Binding Colors}"
							SelectedItem="{TemplateBinding SelectedValue, Mode=TwoWay}">
				<CollectionView.ItemTemplate>
					<DataTemplate>
						<Grid HeightRequest="60">
							<VisualStateManager.VisualStateGroups>
								<VisualStateGroup Name="CommonStates">
									<VisualState Name="Normal">
										<VisualState.Setters>
											<Setter Property="BackgroundColor" Value="White" />
										</VisualState.Setters>
									</VisualState>
									<VisualState Name="Selected">
										<VisualState.Setters>
											<Setter Property="BackgroundColor" Value="WhiteSmoke" />
										</VisualState.Setters>
									</VisualState>
								</VisualStateGroup>
							</VisualStateManager.VisualStateGroups>
							<telerik:RadBorder WidthRequest="40"
											   HeightRequest="40"
											   CornerRadius="20"
											   HorizontalOptions="Center"
											   VerticalOptions="Center"
											   BorderColor="LightGray"
											   BorderThickness="2"
											   BackgroundColor="{Binding}" />
						</Grid>
					</DataTemplate>
				</CollectionView.ItemTemplate>
				<CollectionView.ItemsLayout>
					<GridItemsLayout Orientation="Vertical" Span="5" />
				</CollectionView.ItemsLayout>
			</CollectionView>
		</ControlTemplate>
	</telerikInput:RadTemplatedPicker.SelectorTemplate>
</telerikInput:RadTemplatedPicker>
 ```

1. Add the referenced `ColorViewModel`, which holds the collection with the predefined colors:

 ```C#
 public class ColorViewModel : NotifyPropertyChangedBase
 {
	public ColorViewModel()
	{
		this.Colors = new ObservableCollection<string>
		{
			"#FFFFFF",
			"#EE534F",
			"#AB47BC",
			"#7E57C2",
			"#5D6BC0",
			"#42A5F5",
			"#26C5DA",
			"#24A79A",
			"#66BB6A",
			"#9CCC65",
			"#D4E157",
			"#FFEE58",
			"#FFCA29",
			"#FFA726",
			"#FF7043",
			"#8D6E63",
			"#BDBDBD",
			"#78909C",
			"#3C3C3C",
			"#000000"
		};
	}

	public ObservableCollection<string> Colors { get; }
 }
 ```

1. Add the following namespace:

 ```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
 ```

1. Register the Telerik controls through the `Telerik.Maui.Controls.Compatibility.UseTelerik` extension method called inside the `Configure` method of the `Startup.cs` file of your project:

 ```C#
 using Telerik.Maui.Controls.Compatibility;

 public void Configure(IAppHostBuilder appBuilder)
 {
    appBuilder        
        .UseTelerik()
        .UseMauiApp<App>();    
 }              
 ```



## See Also

- [Visual Structure]({%slug templatedpicker-visual-structure%})
- [Data Binding]({%slug templatedpicker-data-binding%})
- [Templates]({%slug templatedpicker-templates%})
- [Styling]({%slug templatedpicker-styling%})
