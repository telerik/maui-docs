---
title: Styling
page_title: .NET MAUI  ListPicker Documentation | Styling
description: Check our &quot;Styling&quot; documentation article for Telerik ListPicker for .NET MAUI.
position: 8
slug: listpicker-styling
---

# Styling

## ListPicker Styling

ListPicker for .NET MAUI provides the following Style properties for customizing its look:

* `ItemStyle`(of type *Style* with target type **telerikDataControls:SpinnerItemView**): Defines the style applied to the list of items.
* `SelectedItemStyle`(of type *Style* with target type **telerikDataControls:SpinnerItemView**): Defines the style applied to the seledted item.
* `SelectionHighlightStyle`(of type *Style* with target type **telerik:RadBorder**): Specifies the style applied to the border where the current selection is.  
* `PlaceholderLabelStyle`(of type *Style* with target type **Label**): Defines the style applied to the placeholder label.
* `DisplayLabelStyle`(of type *Style* with target type **Label**): Defines the style applied to the label which is visualized when item of the list is selected.

`PickerContentView` class exposes the following properties for styling the ListPicker Border and Background Color:

* `BackgroundColor`: Defines the background color of the picker.
* `BorderColor`: Defines the border color of the picker.
* `BorderThickness`: Specifies the border thickness of the picker. Default value is `new Thickness(0,0,0,1)`.
* `CornerRadius`: Specifies the corner radius of the picker.

## Popup Styling

Using the `SelectorSettings` property (of type *Telerik.XamarinForms.Input.PickerPopupSelectorSettings*) of the ListPicker you can modify the appearance of the dialog (popup). `PickerPopupSelectorSettings` class exposes the following Style properties:

* `PopupViewStyle`(of type *Style* with target type **telerikInput:PickerPopupContentView**): Defines the popup view style.
* `HeaderStyle` (of type *Style* with target type **telerikInput:PickerPopupHeaderView**): Defines the popup header style.
* `HeaderLabelStyle`(of type *Style* with target type **Label**): Defines the popup header label style.
* `FooterStyle`(of type *Style* with target type **telerikInput:PickerPopupFooterView**): Defines the popup footer style.
* `AcceptButtonStyle`(of type *Style* with target type **Button**): Defines the Accept button style.
* `CancelButtonStyle`(of type *Style* with target type **Button**): Defines the Cancel button style.

The `SelectorSettings` also provides the following properties for popup customization:

* `PopupOutsideBackgroundColor`: Defines the color outside of the popup.
* `IsPopupModal`(*bool*): Defines a boolean value indicating if the popup should be closed when tapped outside of the popup. By default the value of the **IsPopupModal** is **false**.
	* When *IsPopupModal="True"*  the UI behind the popup gets inactive and cannot be used until the popup is closed. 
	* When *IsPopupModal="False"* the popup could be closed when clicking outside the popup. 
	
* `HeaderLabelText`(*string*): Specifies the text visualized in the popup header. The default text is **Select Item**.
* `IsHeaderVisible`(*bool*): Specifies whether the Popup header is currently visible. By default the value is *True*.
* `IsFooterVisible`(*bool*): Specifies whether the Popup footer is currently visible. By default the value is *True*.
* `AcceptButtonText`(*string*): Defines the text visualized for the accept button. By default the text is *OK*.
* `CancelButtonText`(*string*): Defines the text visualized for the cancel button. By default the text is *Cancel*. 

## Namespaces

Using `ItemStyle`, `SelectedItemStyle` you need to add the following namespace:

```XAML
xmlns:telerikDataControls="clr-namespace:Telerik.XamarinForms.DataControls;assembly=Telerik.Maui.Controls.Compatibility"
``` 

Using `PopupViewStyle`, `HeaderStyle`, `FooterStyle` add the following namespace:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

`SelectionHighlightStyle` requires the following namespace:

```XAML
xmlns:telerikPrimitives="clr-namespace:Telerik.XamarinForms.Primitives;assembly=Telerik.Maui.Controls.Compatibility"
```

### Example

Here is a sample example that shows how the styling properties are applied.

A sample RadListPicker definition:

<snippet id='listpicker-features-styling' />
```XAML
<telerikInput:RadListPicker Placeholder="Pick a City Name!"
							ItemsSource="{Binding Items}" 
							DisplayMemberPath="Name"
							IsLooping="True"
							DisplayStringFormat="You have picked: {0}"
							DisplayLabelStyle="{StaticResource displayLabelStyle}"
							ItemStyle="{StaticResource ItemStyle}"
							SelectedItemStyle="{StaticResource SelectedItemStyle}"
							PlaceholderLabelStyle="{StaticResource placeholderLabelStyle}">
	<telerikInput:RadListPicker.BindingContext>
		<local:CitiesViewModel/>
	</telerikInput:RadListPicker.BindingContext>
	<telerikInput:RadListPicker.SelectorSettings>
		<telerikInput:PickerPopupSelectorSettings PopupOutsideBackgroundColor="#4A4949F"
												  PopupViewStyle="{StaticResource popupViewStyle}"
												  HeaderStyle="{StaticResource headerStyle}"
												  HeaderLabelText="Select city"
												  HeaderLabelStyle="{StaticResource headerLabelStyle}"
												  FooterStyle="{StaticResource footerStyle}"
												  AcceptButtonStyle="{StaticResource acceptButtonStyle}"
												  CancelButtonStyle="{StaticResource cancelButtonStyle}"/>
	</telerikInput:RadListPicker.SelectorSettings>
</telerikInput:RadListPicker>
```

And here are how the styles are defined in the page resources:

## Item Style

<snippet id='listpicker-features-itemstyle' />

## SelectedItem Style

<snippet id='listpicker-features-selecteditemstyle' />
```XAML
<Style TargetType="telerikDataControls:SpinnerItemView" x:Key="SelectedItemStyle">
	<Setter Property="BackgroundColor" Value="#F0F0F0"/>
	<Setter Property="CornerRadius" Value="0"/>
	<Setter Property="BorderThickness" Value="0"/>
	<Setter Property="TextColor" Value="#4A4949" />
	<Setter Property="FontSize" Value="16"/>
</Style>
```

## PlaceholderLabel Style

<snippet id='listpicker-style-placeholder-label-style' />
```XAML
<Style TargetType="Label" x:Key="placeholderLabelStyle">
	<Setter Property="TextColor" Value="#4A4949"/>
	<Setter Property="VerticalTextAlignment" Value="Center"/>
	<Setter Property="HorizontalTextAlignment" Value="Center"/>
	<Setter Property="HeightRequest" Value="50"/>
</Style>
```

## DisplayLabel Style

<snippet id='listpicker-style-display-label-style' />
```XAML
<Style TargetType="Label" x:Key="displayLabelStyle">
	<Setter Property="TextColor" Value="Black"/>
	<Setter Property="VerticalTextAlignment" Value="Center"/>
	<Setter Property="HorizontalTextAlignment" Value="Center"/>
	<Setter Property="HeightRequest" Value="50"/>
</Style>
```

## PopupView Style

<snippet id='listpicker-style-popupview-style' />
```XAML
<Style TargetType="telerikInput:PickerPopupContentView" x:Key="popupViewStyle">
	<Setter Property="BackgroundColor" Value="White"/>
	<Setter Property="WidthRequest" Value="270"/>
</Style>
```

## Header Style

<snippet id='listpicker-style-header-style' />
```XAML
<Style TargetType="telerikInput:PickerPopupHeaderView" x:Key="headerStyle">
	<Setter Property="BackgroundColor" Value="#1188FF"/>
	<Setter Property="HeightRequest" Value="64"/>
	<Setter Property="Margin" Value="0"/>
	<Setter Property="Padding" Value="0"/>
	<Setter Property="HorizontalOptions" Value="FillAndExpand"/>
	<Setter Property="VerticalOptions" Value="FillAndExpand"/>
</Style>
```

## HeaderLabel Style

<snippet id='listpicker-style-header-label-style' />
```XAML
<Style TargetType="Label" x:Key="headerLabelStyle">
	<Setter Property="TextColor" Value="White"/>
	<Setter Property="HorizontalOptions" Value="Center"/>
	<Setter Property="VerticalOptions" Value="Center"/>
	<Setter Property="FontSize" Value="18"/>
	<Setter Property="FontAttributes" Value="Bold"/>
</Style>
```

## FooterStyle

<snippet id='listpicker-style-footer-style' />
```XAML
<Style TargetType="telerikInput:PickerPopupFooterView" x:Key="footerStyle">
	<Setter Property="BackgroundColor" Value="Transparent"/>
	<Setter Property="HeightRequest" Value="60"/>
</Style>
```

## AcceptButton Style

<snippet id='listpicker-style-accept-button-style' />
```XAML
<Style TargetType="Button" x:Key="acceptButtonStyle">
	<Setter Property="BackgroundColor" Value="Transparent"/>
	<Setter Property="Text" Value="OK"/>
	<Setter Property="TextColor" Value="#1188FF"/>
</Style>
```

## CancelButton Style

<snippet id='listpicker-style-cancel-button-style' />
```XAML
<Style TargetType="Button" x:Key="cancelButtonStyle">
	<Setter Property="BackgroundColor" Value="Transparent"/>
	<Setter Property="Text" Value="CANCEL"/>
	<Setter Property="TextColor" Value="#1188FF"/>
</Style>
```

A sample business model:

<snippet id='listpicker-features-businessmodel' />
```C#
public class City
{
	public string Name { get; set; }
	public int Population { get; set; }
}
```
	
and a ViewModel:

<snippet id='listpicker-features-viewmodel' />
```C#
public class CitiesViewModel
{
	public CitiesViewModel()
	{
		this.Items = new ObservableCollection<City>
		{
			new City { Name = "Tokyo", Population = 13929286 },
			new City { Name = "New York", Population = 8623000 },
			new City { Name = "London", Population = 8908081 },
			new City { Name = "Madrid", Population = 3223334 },
			new City { Name = "Los Angeles", Population = 4000000},
			new City { Name = "Paris", Population = 2141000 },
			new City { Name = "Beijing", Population = 21540000 },
			new City { Name = "Singapore", Population = 5612000 },
			new City { Name = "New Delhi", Population = 18980000 },
			new City { Name = "Bangkok", Population = 8305218 },
			new City { Name = "Berlin", Population = 3748000 },
		};
	}

	public ObservableCollection<City> Items { get; set; }
}
```

also you will need to add the following namespaces:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
xmlns:telerikDataControls="clr-namespace:Telerik.XamarinForms.DataControls;assembly=Telerik.Maui.Controls.Compatibility"
```

This is how the ListPicker looks when the styling properties are applied:

![ListPicker Styling](images/listpicker_styling.png)

>important A sample Styling example can be found in the ListPicker/Styling folder of the [Telerik UI for .NET MAUI SDKBrowser Application]({%slug maui-demo-app%}).

## See Also

- [Looping]({%slug listpicker-looping%})
- [Templates]({%slug listpicker-templates%})
