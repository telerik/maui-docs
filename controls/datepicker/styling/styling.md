---
title: Picker Styling
page_title: .NET MAUI DatePicker Documentation - Styling
description: Learn what are the styling options for customizing the appearance of the Telerik UI for .NET MAUI DatePicker control.
position: 0
slug: datepicker-styling
---

# Styling the .NET MAUI DatePicker

The DatePicker control for .NET MAUI provides styling options for customizing its appearance. You can style the DatePicker itself, as well as its popup or drop-down depending on the configuration of the [picker mode]({%slug datepicker-picker-mode%}).

## Supported Properties

The DatePicker control supports the following styling properties:

* `BackgroundColor`&mdash;Defines the background color of the picker.
* `BorderColor`&mdash;Defines the border color of the picker.
* `BorderThickness`&mdash;Specifies the border thickness of the picker. Its default value is `new Thickness(0,0,0,1)`.
* `CornerRadius`&mdash;Specifies the corner radius of the picker.
* `ClearButtonStyle`(of type `Style` with target type `RadButton`)&mdash;Defines the style applied to the [Clear button]({%slug datepicker-selection%}#clear-button).
* `ToggleButtonStyle`(of type `Style` with target type `RadButton`)&mdash;Specifies the style of the [Toggle button]({%slug datepicker-picker-mode%}##toggle-button).
* `PlaceholderLabelStyle`(of type `Style` with target type `Label`)&mdash;Specifies the style applied to the label defined in the [default PlaceholderTemplate]({%slug datepicker-templates%}#default-placeholdertemplate).
* `DisplayLabelStyle`(of type `Style` with target type `Label`)&mdash;Defines the style applied to the label, which is visualized when a date is selected.


The following `Style` properties are related to the spinner controls inside the popup or drop-down:

* `SpinnerStyle`(of type `Style` with target type `telerik:RadSpinner`)&mdash;Defines the style applied to the spinner item and the selected item.
* `SpinnerHeaderStyle`(of type `Style` with target type `Label`)&mdash;Specifies the style applied to each spinner header label.
* `SelectionHighlightStyle`(of type `Style` with target type `telerik:RadBorder`)&mdash;Specifies the style applied to the border that highlights the selection.

## Setting the Properties

The following examples demonstrate how to use the styling properties of the DatePicker. Note that in addition to each snippet, you must add the `telerik` namespaces:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

>caption Define the style of the DatePicker

<snippet id='datepicker-style' />

>caption Define the style of the spinner

<snippet id='datepicker-style-spinner-style' />

>caption Define the style of the spinner header

<snippet id='datepicker-style-spinner-header-style' />

>caption Define the highlight style of the selection

<snippet id='datepicker-style-selection-highlight-style' />

>caption Define the style of the placeholder label

<snippet id='datepicker-style-placeholder-label-style' />

>caption Define the style of the displayed label

<snippet id='datepicker-style-display-label-style' />

>caption Define the style of the Clear button

<snippet id='datepicker-style-clear-button-style' />

>caption Define the style of the Toggle button

<snippet id='datepicker-style-toggle-button-style' />

The following image shows a DatePicker control on different platforms after the styles have been applied:

![Telerik UI for .NET MAUI DatePicker with applied styling properties](../images/datepicker_style.png)

## See Also

- [Setting Date Ranges in the .NET MAUI DatePicker]({%slug datepicker-date-range%})
- [.NET MAUI DatePicker Templates]({%slug datepicker-templates%})
- [.NET MAUI DatePicker Selection]({%slug datepicker-selection%})
- [.NET MAUI DatePicker Product Page](https://www.telerik.com/maui-ui/datepicker)
