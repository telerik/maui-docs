---
title: TimePicker, DatePicker, and ComboBox DropDown Not Displaying Correctly in Toolkit Popup
description: Addressing the issue where TimePicker, DatePicker, and ComboBox dropdowns or popups are not displayed correctly on iOS and Mac when placed in Mopups.
type: troubleshooting
page_title: Dropdowns and Pickers Not Rendering Properly Inside Mopups in .NET MAUI
meta_title: Dropdowns and Pickers Not Rendering Properly Inside Mopups in .NET MAUI
slug: dropdowns-pickers-not-rendering-inside-mopups
tags: timepicker, .net maui, combobox, mopups, community toolkit, modal page
res_type: kb
---

## Environment

| Product | Author | 
| --- | ---- | 
| Telerik UI for .NET MAUI ComboBox | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |
| Telerik UI for .NET MAUI AutoComplete | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |
| Telerik UI for .NET MAUI Pickers | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |
| Telerik UI for .NET MAUI Popup | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

In my .NET MAUI app, TimePicker, DatePicker, ComboBox dropdown, and other pickers' popups do not display correctly on iOS and Mac when placed inside Mopups or CommunityToolkit Popups. Instead, they either render behind the popup or fail to display at all. Previously, adjustments allowed proper rendering on top of everything, but the behavior persists due to nested popup limitations.

## Cause

The issue occurs because Telerik controls like [TimePicker](https://docs.telerik.com/devtools/maui/controls/timepicker/overview), [ComboBox](https://docs.telerik.com/devtools/maui/controls/combobox/overview), and other pickers rely on `RadPopup` to render their dropdowns and popups. When these controls are nested inside Mopups or CommunityToolkit Popups, rendering issues arise due to conflicting popup layers. This limitation is documented in a logged item on Telerik's feedback portal.

## Solution

To resolve the issue, use a modal page instead of Mopups or CommunityToolkit Popups for presenting content. Modal pages do not experience the clipping and rendering issues associated with nested popups. Follow these steps:

**1.** Define a button to open the modal page.

```xaml
<Grid RowDefinitions="Auto">
	<telerik:RadButton Text="Open Popup"
						Clicked="RadButton_Clicked" />
</Grid>
```

**2.** Handle the button click to open the modal page.

```c#
private async void RadButton_Clicked(object sender, EventArgs e)
{
	var modalPage = new MyAutoCompletePopup();
	await this.Navigation.PushModalAsync(modalPage);
}
```

**3.** Create the modal page as a `ContentPage` to host the controls.

```xaml
<ContentPage xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
			 xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
             x:Class="MauiApp.MyAutoCompletePopup"
			 BackgroundColor="#80000000"
             Title="MyAutoCompletePopup">
	<Grid VerticalOptions="Center" HorizontalOptions="Center">
		<telerik:RadBorder Padding="20"
                           WidthRequest="300"
                           HeightRequest="500"
                           BackgroundColor="White"
                           CornerRadius="12">

			<VerticalStackLayout Spacing="15">
				<telerik:RadAutoComplete x:Name="autoComplete" Placeholder="Search here..."/>

				<Button Text="Ok"
                        Clicked="OnOkClicked"
                        HorizontalOptions="Center" />
			</VerticalStackLayout>
		</telerik:RadBorder>
	</Grid>
</ContentPage>
```

Replace `RadAutoComplete` and other controls as needed for your application's functionality.

## See Also

- [TimePicker Documentation](https://docs.telerik.com/devtools/maui/controls/timepicker/overview)
- [ComboBox Documentation](https://docs.telerik.com/devtools/maui/controls/combobox/overview)
- [Feedback Item on Nested Popups](https://feedback.telerik.com/maui/1677597-combobox-pickers-ios-maccatalyst-displayed-in-wrong-window-when-inside-mopups)
