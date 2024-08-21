---
title: Styling
page_title: .NET MAUI ComboBox Documentation - Styling
description: Learn more about styling options in Telerik UI for .NET MAUI ComboBox control.
position: 15
slug: combobox-styling
---

# .NET MAUI ComboBox Styling

The [Telerik UI for .NET MAUI ComboBox]({%slug combobox-overview%}) provides the following Style properties for customizing its look:

* `PlaceholderColor` (`Microsoft.Maui.Graphics.Color`)&mdash;Defines the color for the placeholder text.
* `TextColor` (`Microsoft.Maui.Graphics.Color`)&mdash;Defines the color of the text when the control is editable and the color of the selected item when the control is not editable and the selection mode is single.
* `BackgroundColor` (`Microsoft.Maui.Graphics.Color`)&mdash;Defines the background color of the control.
* `BorderColor` (`Microsoft.Maui.Graphics.Color`)&mdash;Defines the color of the border.
* `BorderThickness` (`Microsoft.Maui.Thickness`)&mdash;Defines the thickness of the border.
* `ClearButtonStyle` (of type `Style` with target type `Telerik.Maui.Controls.RadButton`)&mdash;Defines the style for the clear button.
* `Font Options` (`FontAttributes`, `FontFamily`, `FontSize`)&mdash;Define the font options to the text of the RadComboBox. It's applied to the Placeholder, Selected Text(for single selection) and when the control is in Editable Mode.
* `HighlightTextColor` (`Color`)&mdash;Specifies the color of the text that will be highlighted when searching isperformed (`IsEditable` has to be `True`).

### Example for ComboBox Styling

**1.** Define the ComboBox in XAML:

<snippet id='combobox-styling'/>

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Add sample business model:

<snippet id='combobox-city-businessmodel'/>

**4.** Add the `ViewModel`:

<snippet id='comobobox-editing-viewmodel'/> 

Here is how the ComboBox looks when styling is applied:

![.NET MAUI ComboBox Styling](images/combobox-styling.png)

Here is how the styling is applied when the control is focused and item is selected:

![.NET MAUI ComboBox Styling on Selected Item](images/combobox-styling-focused.png)

> For the ComboBox Styling example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to the **ComboBox > Styling** category.

## DropDown Styling

The following properties styles the ComboBox Drop Down:

* `DropDownBorderColor`(`Microsoft.Maui.Graphics.Color`): Defines the color of the border around the drop down part of the control.
* `DropDownBorderThickness`(`Microsoft.Maui.Thickness`): Defines the thickness of the border that is around of the drop down part of the control.
* `DropDownBorderCornerRadius`(`Microsoft.Maui.Thickness`): Defines the corner radius of the border that is around the drop down part of the control
* `DropDownBackgroundColor`(`Microsoft.Maui.Graphics.Color`): Defines the background color of the drop down part of the control.
* `DropDownButtonStyle`(of type `Style` with target type `Telerik.Maui.Controls.RadButton`): Defines the style for the drop down button.

### Example for DropDown Styling

**1.** Define the ComboBox in XAML:

<snippet id='combobox-dropdown-styling'/>

**2.** Add the `telerik` namespace:

<snippet id='xmlns-telerikinput'/>

**3.** Define the DropDown Button Style in the Page's ResourceDictionary:

<snippet id='combobox-dropdownbutton-style'/>

**4.** Add sample business model:

<snippet id='combobox-city-businessmodel'/>

**5.** Add the `ViewModel` used:

<snippet id='comobobox-editing-viewmodel'/> 

Here is how the Drop Down Styling looks on Android:

![ComboBox Drop Down Style](images/combobox-drop-down-style.png)

> For the ComboBox DropDown Styling example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to ComboBox -> Styling category.

## See Also

- [Configuration]({% slug combobox-configuration%})
