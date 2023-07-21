---
title: Drop-Down Styling
page_title: .NET MAUI DatePicker Documentation - Drop-Down Styling
description: Apply the styling options supported by the Telerik UI for .NET MAUI DatePicker component to its drop-down element.
position: 2
slug: datepicker-dropdown-styling
---

# Styling the .NET MAUI DatePicker Drop-Down

To modify the appearance of the DatePicker drop-down element, use the `DropDownSettings` property (of type `Telerik.Maui.Controls.PickerDropDownSettings`) of the component.

## Supported Properties

The `PickerDropDownSettings` class exposes the following `Style` properties:

* `DropDownViewStyle`(of type `Style` with target type `telerik:PickerDropDownContentView`)&mdash;Defines the drop-down view style.
* `FooterStyle`(of type `Style` with target type `telerik:PickerPopupFooterView`)&mdash;Defines the drop-down footer style.
* `AcceptButtonStyle`(of type `Style` with target type `Button`)&mdash;Defines the **Accept** button style.
* `CancelButtonStyle`(of type `Style` with target type `Button`)&mdash;Defines the **Cancel** button style.

The `DropDownSettings` also provides the following properties for drop-down customization:

* `Placement`(of type `PlacementMode`)&mdash;Specifies the position of the drop-down. Can be set to `Bottom`, `Right`, `Left`, `Top`, `Center`, or `Relative`.
* `HorizontalOffset` or `VerticalOffset`&mdash;Specifies the horizontal or vertical distance between the drop-down and the DatePicker.
* `IsFooterVisible`(`bool`)&mdash;Specifies whether the footer of the drop-down is currently visible. By default, the value is `True`.
* `AcceptButtonText`(`string`)&mdash;Defines the text visualized for the **Accept** button. By default, the text is `OK`.
* `CancelButtonText`(`string`)&mdash;Defines the text visualized for the **Cancel** button. By default, the text is `Cancel`.

> `DropDownSettings` provides styling options for the drop-down, its footer, position, and other. To customize the look and feel of the spinner controls which show the available date values, [use the `SpinnerStyle`, `SpinnerHeaderStyle`, and `SelectionHighlightStyle` properties of the DatePicker]({%slug datepicker-styling%}).

## Setting the Properties

The following examples demonstrate how to define and use the styling properties of the DatePicker popup. Note that in addition to each snippet, you must add the `telerik` namespaces:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

>caption Define the style of the DatePicker

<snippet id='datepicker-dropdown-style' />

>caption Define the style of the drop-down view

<snippet id='datepicker-style-dropdownview-style' />

>caption Define the style of the footer

<snippet id='datepicker-style-footer-style' />

>caption Define the style of the Accept button

<snippet id='datepicker-style-accept-button-style' />

>caption Define the style of the Cancel button

<snippet id='datepicker-style-cancel-button-style' />


The following image shows a DatePicker control on different platforms after the styles have been applied to its drop-down:

![Telerik UI for .NET MAUI DatePicker with applied styling properties to its drop-down](../images/datepicker_dropdown_styling.png)

## See Also

- [Setting Date Ranges in the .NET MAUI DatePicker]({%slug datepicker-date-range%})
- [.NET MAUI DatePicker Templates]({%slug datepicker-templates%})
- [.NET MAUI DatePicker Selection]({%slug datepicker-selection%})
- [.NET MAUI DatePicker Product Page](https://www.telerik.com/maui-ui/datepicker)
