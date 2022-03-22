---
title: DateTimePicker Styling
page_title: .NET MAUI DateTimePicker Documentation | Styling
description: "Apply the styling options of the Telerik UI for .NET MAUI DateTimePicker and set the appearance of the control and its popup."
position: 0
slug: datetimepicker-styling
---

# DateTimePicker Styling

The DateTimePicker control for .NET MAUI provides styling options for customizing its appearance. You can style the DateTimePicker itself, as well as its popup or dropdown depending on the [PickerMode]({%slug datetimepicker-picker-mode%}) setting.


The control supports the following styling properties:

* `BackgroundColor`&mdash;Defines the background color of the picker.
* `BorderColor`&mdash;Defines the border color of the picker.
* `BorderThickness`&mdash;Specifies the border thickness of the picker. Its default value is `new Thickness(0,0,0,1)`.
* `CornerRadius`&mdash;Specifies the corner radius of the picker.
* `ClearButtonStyle`(of type `Style` with target type `RadButton`)&mdash;Defines the style applied to the [Clear button]({%slug datetimepicker-selection%}#clear-button).
* `ToggleButtonStyle`(of type `Style` with target type `RadButton`)&mdash;Specifies the style of the [Toggle button]({%slug datetimepicker-picker-mode%}##toggle-button).
* `PlaceholderLabelStyle`(of type `Style` with target type `Label`)&mdash;Specifies the style applied to the label defined in the [default PlaceholderTemplate]({%slug datetimepicker-templates%}#default-placeholdertemplate).
* `DisplayLabelStyle`(of type `Style` with target type `Label`)&mdash;Defines the style applied to the label, which is visualized when a date is selected.

The following Style properties are related to the spinner controls inside the popup/dropdown:


* `SpinnerStyle`(of type `Style` with target type `telerikDataControls:RadSpinner`)&mdash;Defines the style applied to the spinner item and the selected item.
* `SpinnerHeaderStyle`(of type `Style` with target type `Label`)&mdash;Specifies the style applied to each spinner header label.
* `SelectionHighlightStyle`(of type `Style` with target type `telerikPrimitives:RadBorder`)&mdash;Specifies the style applied to the border that highlights the selection.

## Namespaces

When you use `SelectionHighlightStyle`, you need to add the following namespace:

```XAML
xmlns:telerik="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
```

When you use `SpinnerStyle`, you need to add the following namespace:

```XAML
xmlns:telerikDataControls="clr-namespace:Telerik.XamarinForms.DataControls;assembly=Telerik.Maui.Controls.Compatibility"
```

## Styling Examples

The following examples demonstrate how to define use the styling properties of the DateTimePicker.

**Define the `RadDateTimePicker`**

<snippet id='datepicker-style' />

**Define the Spinner Style**

<snippet id='datepicker-style-spinner-style' />

**Define the SpinnerHeaderStyle**

<snippet id='datepicker-style-spinner-header-style' />

**Define the SelectionHighlightStyle**

<snippet id='datepicker-style-selection-highlight-style' />

**Define the PlaceholderLabelStyle**

<snippet id='datepicker-style-placeholder-label-style' />

**Define the DisplayLabelStyle**

<snippet id='datepicker-style-display-label-style' />

**Define the ClearButtonStyle**

<snippet id='datepicker-style-clear-button-style' />

**Define the ToggleButtonStyle**

<snippet id='datepicker-style-toggle-button-style' />

In addition, add the following namespaces:

 ```XAML
xmlns:telerikDataControls="clr-namespace:Telerik.XamarinForms.DataControls;assembly=Telerik.Maui.Controls.Compatibility"
xmlns:telerik="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
 ```

The following image shows what the DateTimePicker control looks like when the styles described above are applied:

![DateTimePicker](../images/datepicker_style.png)

## See Also

- [Picker Mode]({%slug datetimepicker-picker-mode%})
- [Formatting]({%slug datetimepicker-formatting%})
- [Templates]({%slug datetimepicker-templates%})
- [Commands]({%slug datetimepicker-commands%})
- [Visual Structure]({%slug datetimepicker-visual-structure%})
