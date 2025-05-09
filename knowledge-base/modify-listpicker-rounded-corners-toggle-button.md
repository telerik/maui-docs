---
title: Modifying ListPicker with Rounded Corners and Toggle Button Indicators
description: Learn how to modify the ListPicker control in .NET MAUI to include rounded corners and toggle button indicators for dropdown functionality.
type: how-to
page_title: Styling ListPicker with Rounded Corners and Dropdown Indicators in .NET MAUI
slug: modify-listpicker-rounded-corners-toggle-button
tags: listpicker, .net maui, styling, borders, togglebutton, dropdown
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 10.1.0 | Telerik UI for .NET MAUI ListPicker | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to customize the ListPicker control in .NET MAUI to display rounded corners and dropdown indicators with up and down arrows depending on whether the control is open or closed.

This knowledge base article also answers the following questions:
- How to add borders to ListPicker in .NET MAUI?
- How to create toggle button styles for ListPicker?
- How to show dropdown indicators in ListPicker?

## Solution

To style the ListPicker with rounded corners and toggle button indicators, follow the steps below:

### Adding Rounded Corners

Use the `BorderColor` and `BorderThickness` properties of the [`RadListPicker`](https://docs.telerik.com/devtools/maui/controls/listpicker/styling/styling) to define the border color and thickness. For example:

```xaml
<telerik:RadListPicker BorderColor="#8660C5"
                                        BorderThickness="2"
                                        PickerMode="DropDown"
                                        IsToggleButtonVisible="True">
</telerik:RadListPicker>
```

### Implementing Toggle Button Indicators

Use custom `ToggleButtonStyle` and dynamically switch between styles based on the `RadListPicker.IsOpen` property.

#### Step 1: Define Toggle Button Styles

Add the following styles to the `ResourceDictionary` in your XAML file:

```xaml
<ContentPage.Resources>
    <ResourceDictionary>
        <Style x:Key="toggleButtonStyle" TargetType="Button">
            <Setter Property="Text" Value="&#xE812;" /> <!-- Down Arrow -->
            <Setter Property="Padding" Value="0" />
            <Setter Property="WidthRequest" Value="30" />
            <Setter Property="HeightRequest" Value="30" />
            <Setter Property="BorderWidth" Value="1" />
            <Setter Property="BorderColor" Value="Red" />
            <Setter Property="BackgroundColor" Value="Transparent" />
            <Setter Property="VerticalOptions" Value="Center" />
            <Setter Property="FontFamily" Value="TelerikFont" />
            <Setter Property="FontSize" Value="14" />
        </Style>

        <Style x:Key="toggleButtonStyleToggled" TargetType="Button">
            <Setter Property="Text" Value="^" /> <!-- Up Arrow -->
            <Setter Property="Padding" Value="0" />
            <Setter Property="WidthRequest" Value="30" />
            <Setter Property="HeightRequest" Value="30" />
            <Setter Property="BorderWidth" Value="1" />
            <Setter Property="BorderColor" Value="Blue" />
            <Setter Property="BackgroundColor" Value="Transparent" />
            <Setter Property="VerticalOptions" Value="Center" />
            <Setter Property="FontFamily" Value="TelerikFont" />
            <Setter Property="FontSize" Value="14" />
        </Style>
    </ResourceDictionary>
</ContentPage.Resources>
```

#### Step 2: Bind Toggle Button Style to `RadListPicker`
Set the `ToggleButtonStyle` property in the `RadListPicker`:

```xaml
<telerik:RadListPicker ToggleButtonStyle="{StaticResource toggleButtonStyle}"
                       IsToggleButtonVisible="True" x:Name="picker"
                       BorderColor="#8660C5" BorderThickness="2"
                       PickerMode="DropDown">
</telerik:RadListPicker>
```

#### Step 3: Handle Property Changes in Code-Behind
Add the `RadListPicker_PropertyChanged` handler to dynamically switch styles based on the `IsOpen` property:

```csharp
private void RadListPicker_PropertyChanged(object sender, System.ComponentModel.PropertyChangedEventArgs e)
{
    if (e.PropertyName == "IsOpen" && this.picker.IsOpen == true)
    {
        this.picker.ToggleButtonStyle = this.Resources["toggleButtonStyleToggled"] as Style;
    }
    else if (e.PropertyName == "IsOpen" && this.picker.IsOpen == false)
    {
        this.picker.ToggleButtonStyle = this.Resources["toggleButtonStyle"] as Style;
    }
}
```

### Notes

The above implementation adds rounded borders and dynamically updates the toggle button style to display up and down arrows based on the state of the dropdown.

## See Also

- [RadListPicker Styling Documentation](https://docs.telerik.com/devtools/maui/controls/listpicker/styling/styling)
- [RadListPicker Overview](https://docs.telerik.com/devtools/maui/controls/listpicker/overview)
- [PickerDropDownSettings](https://docs.telerik.com/devtools/maui/api/telerik.maui.controls.pickerdropdownsettings)
