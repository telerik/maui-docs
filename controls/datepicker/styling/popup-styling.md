---
title: Popup Styling
page_title: .NET MAUI DatePicker Documentation | Popup Styling
description: "Apply the styling options of the Telerik UI for .NET MAUI DatePicker Popup."
position: 1
slug: datepicker-popup-styling
---

# Popup Styling

By using the `PopupSettings` property (of type `Telerik.Maui.Controls.PickerPopupSettings`) of the DatePicker, you can modify the appearance of the dialog (popup). 

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

> __PopupSettings__ provides styling options for the popup, its header and footer, outside background color and other. If you need to customize the look&feel of the spinner controls that show the available date values, please refer to `SpinnerStyle`, `SpinnerHeaderStyle` and `SelectionHighlightStyle` properties of the DatePicker. For more detailed information on them go to [DatePicker Styling]({%slug datepicker-styling%}) topic.

## Example

The following examples demonstrate how to define use the styling properties of the DatePicker.

**Define the `RadDatePicker`**

<snippet id='datepicker-popup-style' />

**Define the PopupViewStyle**

<snippet id='datepicker-style-popupview-style' />

**Define the HeaderStyle**

<snippet id='datepicker-style-header-style' />

**Define the HeaderLabelStyle**

<snippet id='datepicker-style-header-label-style' />

**Define the FooterStyle**

<snippet id='datepicker-style-footer-style' />

**Define the AcceptButtonStyle**

<snippet id='datepicker-style-accept-button-style' />

**Define the CancelButtonStyle**

<snippet id='datepicker-style-cancel-button-style' />

In addition, add the following namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

The following image shows what the DatePicker control looks like when the styles described above are applied:

![DatePicker](../images/datepicker_popup_styling.png)

## See Also

- [DatePicker Styling]({%slug datepicker-styling%})
- [Formatting]({%slug datepicker-formatting%})
- [Visual Structure]({%slug datepicker-visual-structure%})
