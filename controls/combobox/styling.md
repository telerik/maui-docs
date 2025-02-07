---
title: Styling
page_title: .NET MAUI ComboBox Documentation - Styling
description: Learn more about styling options in Telerik UI for .NET MAUI ComboBox control.
position: 15
slug: combobox-styling
---

# .NET MAUI ComboBox Styling

The [Telerik UI for .NET MAUI ComboBox]({%slug combobox-overview%}) provides the following Style properties for customizing its look:

* `PlaceholderColor`(`Color`)&mdash;Defines the color for the placeholder text.
* `TextColor`(`Color`)&mdash;Defines the following colors:
	* The color of the text when the control is editable.
	* The color of the selected item when the control is not editable and the selection mode is single.
* `HighlightTextColor`(`Color`)&mdash;Specifies the color of the text that will be highlighted when searching (`IsEditable` must be `True`).
* `BackgroundColor`(`Color`)&mdash;Defines the background color of the control.
* `BorderColor`(`Color`)&mdash;Defines the color of the border.
* `BorderThickness`(`Thickness`)&mdash;Defines the thickness of the border.
* `ClearButtonStyle` (of type `Style` with target type `Telerik.Maui.Controls.RadTemplatedButton`)&mdash;Defines the style for the clear button.
* `Font Options`(`FontAttributes`, `FontFamily`, `FontSize`)&mdash;Defines the font options for the text of the ComboBox. It's applied to the Placeholder and Selected Text (for single selection) and when the control is in Editable Mode.

The ComboBox control uses the [`RadTextInput`]({%slug entry-textinput%}) control internally when the ComboBox `IsEditable` property is set to `True`. To style the input control (`RadTextInput`), use the `TextInputStyle` (of type `Style` with target type `Telerik.Maui.Controls.RadTextInput`).

In addition to the available styling properties, you can apply specific [Visual States]({%slug combobox-visual-states%}) to the ComboBox control.

### Example for ComboBox Styling

The example below demonstrates some of the styling capabilities of the ComboBox, such as custom `ClearButtonStyle`, `TextInputStyle`, `TextColor`, `PlaceholderColor`, and others. It also shows how to switch its appearance through the .NET MAUI Visual State Manager.

The example uses the same `ViewModel` and `City` classes as the [Getting Started]({%slug combobox-getting-started%}) topic.

**1.** Add a Style that targets the `RadComboBox` to your page's resources and apply all the needed styling properties and the visual states:

<snippet id='combobox-custom-styles' />

**2.** Define the ComboBox in XAML:

<snippet id='combobox-styling-xaml'/>

Here is how the ComboBox looks when styling is applied:

![.NET MAUI ComboBox Styling](images/combobox-styling.png)

Here is how the styling is applied when the control is focused and item is selected:

![.NET MAUI ComboBox Styling on Selected Item](images/combobox-styling-focused.png)

> For the ComboBox Styling example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to the **ComboBox > Styling** category.

## DropDown Styling

The following properties style the ComboBox DropDown:

* `DropDownBorderColor`(`Color`)&mdash;Defines the color of the border that surrounds the DropDown part of the control.
* `DropDownBorderThickness`(`Thickness`)&mdash;Defines the thickness of the border that surrounds the DropDown part of the control.
* `DropDownBorderCornerRadius`(`Thickness`)&mdash;Defines the corner radius of the border that surrounds the DropDownn part of the control.
* `DropDownBackgroundColor`(`Color`)&mdash;Defines the background color of the DropDown part of the control.
* `DropDownButtonStyle`(of type `Style` with target type `Telerik.Maui.Controls.RadTemplatedButton`)&mdash;Defines the style for the DropDown button.

### Example for DropDown Styling

**1.** Define the DropDown Button Style in the page's resources:

<snippet id='combobox-dropdownbutton-style'/>

**2.** Define the ComboBox in XAML:

<snippet id='combobox-dropdown-styling'/>

Here is how the Drop Down Styling looks:

![ComboBox Drop Down Style](images/combobox-drop-down-style.png)

> For the ComboBox DropDown Styling example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to ComboBox -> Styling category.

## See Also

- [Configuration]({% slug combobox-configuration%})
- [Edit Mode & Search]({%slug combobox-editmode-and-search%})
