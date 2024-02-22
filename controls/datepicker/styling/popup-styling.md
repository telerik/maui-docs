---
title: Popup Styling
page_title: .NET MAUI DatePicker Documentation - Popup Styling
description: Learn how to style the elements in the popup part of the Telerik UI for .NET MAUI DatePicker.
position: 1
slug: datepicker-popup-styling
---

# Styling the .NET MAUI DatePicker Popup

To modify the appearance of the DatePicker dialog (popup) element, use the `PopupSettings` property (of type `Telerik.Maui.Controls.PickerPopupSettings`) of the component.

## Supported Properties

The `PickerPopupSettings` class exposes the following `Style` properties:

* `PopupViewStyle`(of type `Style` with target type `telerik:PickerPopupContentView`)&mdash;Defines the popup view style.
* `HeaderStyle`(of type `Style` with target type `telerik:PickerPopupHeaderView`)&mdash;Defines the popup header style.
* `HeaderLabelStyle`(of type `Style` with target type `Label`)&mdash;Defines the popup header label style.
* `FooterStyle`(of type `Style` with target type `telerik:PickerPopupFooterView`)&mdash;Defines the popup footer style.
* `AcceptButtonStyle`(of type `Style` with target type `Button`)&mdash;Defines the **Accept** button style.
* `CancelButtonStyle`(of type `Style` with target type `Button`)&mdash;Defines the **Cancel** button style.


The `PickerPopupSettings` also provides the following properties for popup customization:

* `PopupOutsideBackgroundColor`&mdash;Defines the color outside of the popup.
* `IsPopupModal`(`bool`)&mdash;Defines a Boolean value indicating if the popup will be closed when tapped outside of the popup. By default, the value of the `IsPopupModal` is `false`.

	When `IsPopupModal="True"`, the UI behind the popup gets inactive and cannot be used until the popup is closed.

	When `IsPopupModal="False"`, the popup can be closed when clicking outside the popup. 	

* `HeaderLabelText`(`string`)&mdash;Specifies the text visualized in the popup header.
* `IsHeaderVisible`(`bool`)&mdash;Specifies whether the Popup header is currently visible. By default, the value is `True`
* `IsFooterVisible`(`bool`)&mdash;Specifies whether the Popup footer is currently visible. By default, the value is `True`.
* `AcceptButtonText`(`string`)&mdash;Defines the text visualized for the **Accept** button. By default, the text is `OK`.
* `CancelButtonText`(`string`)&mdash;Defines the text visualized for the **Cancel** button. By default, the text is `Cancel`.

> `PopupSettings` provides styling options for the popup, its header, footer, outside background color, and other. To customize the look and feel of the spinner controls which show the available date values, [use the `SpinnerStyle`, `SpinnerHeaderStyle`, and `SelectionHighlightStyle` properties of the DatePicker]({%slug datepicker-styling%}).

## Setting the Properties

The following examples demonstrate how to define and use the styling properties of the DatePicker popup. Note that in addition to each snippet, you must add the `telerik` namespaces:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

>caption Define the style of the DatePicker

<snippet id='datepicker-popup-style' />

>caption Define the style of the popup view

<snippet id='datepicker-style-popupview-style' />

>caption Define the header style

<snippet id='datepicker-style-header-style' />

>caption Define the style of the header label

<snippet id='datepicker-style-header-label-style' />

>caption Define the style of the footer

<snippet id='datepicker-style-footer-style' />

>caption Define the style of the Accept button

<snippet id='datepicker-style-accept-button-style' />

>caption Define the style of the Cancel button

<snippet id='datepicker-style-cancel-button-style' />

The following image shows a DatePicker control on different platforms after the styles have been applied to its popup:

![Telerik UI for .NET MAUI DatePicker with applied styling properties to its popup](../images/datepicker_popup_styling.png)

## See Also

- [Setting Date Ranges in the .NET MAUI DatePicker]({%slug datepicker-date-range%})
- [.NET MAUI DatePicker Templates]({%slug datepicker-templates%})
- [.NET MAUI DatePicker Selection]({%slug datepicker-selection%})
- [.NET MAUI DatePicker Product Page](https://www.telerik.com/maui-ui/datepicker)
