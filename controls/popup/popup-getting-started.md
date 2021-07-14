---
title: Getting Started
page_title: Getting Started with .NET MAUI Popup Control
description: Check our &quot;Getting Started&quot; documentation article for Telerik Popup for .NET MAUI control.
position: 1
slug: popup-getting-started
---

# Getting Started
	
#### Define RadPopup control

The next example shows a sample RadPopup attached to a Button control. The purpose of the Popup in this scenario is to receive user input - it contains Entry control for allowing the user to enter a comment and a button for closing the popup.

Check below the Popup definition in XAML and in code-behind:

```XAML
<Button HorizontalOptions="Center" 
	VerticalOptions="Start" 
	Text="Add a comment" 
	Clicked="ShowPopup">
	<telerikPrimitives:RadPopup.Popup>
		<telerikPrimitives:RadPopup x:Name="popup"
									IsModal="True"
									OutsideBackgroundColor="#6F000000">
			<telerikMauiControls:RadBorder CornerRadius="8" 
										   BackgroundColor="Wheat">
				<Grid Padding="20"
					  WidthRequest="200"
					  HeightRequest="100">
					<Grid.RowDefinitions>
						<RowDefinition Height="30" />
						<RowDefinition Height="40" />
					</Grid.RowDefinitions>
					<Entry Placeholder="add a note here" />
					<Button Grid.Row="1"
						Padding="2"
						HorizontalOptions="End" 
						Text="Send" 
						Clicked="ClosePopup" />
				</Grid>
			</telerikMauiControls:RadBorder>
		</telerikPrimitives:RadPopup>
	</telerikPrimitives:RadPopup.Popup>
</Button>
```

And here are the referenced event handlers:

```C#
private void ClosePopup(object sender, EventArgs e)
{
    popup.IsOpen = false;
}
private void ShowPopup(object sender, EventArgs e)
{
    popup.IsOpen = true;
}
```

In addition to this, you need to add the following namespace (*telerikMauiControls* namespace is needed for the Border control used in the example, in general it's not required for RadPopup):

```XAML
xmlns:telerikPrimitives="clr-namespace:Telerik.XamarinForms.Primitives;assembly=Telerik.Maui.Controls.Compatibility"
xmlns:telerikMauiControls="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
```

This is the result:

![RadPopup](images/popup_getting_started.png)

## See Also

- [Modal Popup Support]({%slug popup-key-features%}#modal-popup)
- [Placement Configuration]({%slug popup-key-features%}#placement-configuration)
- [Animation Settings]({%slug popup-key-features%}#animation-settings)