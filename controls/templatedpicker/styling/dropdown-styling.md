---
title: DropDown Styling
page_title: .NET MAUI TemplatedPicker Documentation - DropDown Styling
description: Check our &quot;DropDown Styling&quot; documentation article for Telerik TemplatedPicker for .NET MAUI.
position: 2
slug: templatedpicker-dropdown-styling
---

# .NET MAUI TemplatedPicker DropDown Styling

By using the `DropDownSettings` property (of type `Telerik.XamarinForms.Input.PickerDropDownSettings`) of the TemplatedPicker, you can modify the appearance of the dropdown. The `PickerDropDownSettings` class exposes the following `Style` properties:

* `DropDownViewStyle`(of type `Style` with target type `telerikInput:PickerDropDownContentView`)&mdash;Defines the dropdown view style.
* `FooterStyle`(of type `Style` with target type `telerikInput:PickerPopupFooterView`)&mdash;Defines the dropdown footer style.
* `AcceptButtonStyle`(of type `Style` with target type `Button`)&mdash;Defines the **Accept** button style.
* `CancelButtonStyle`(of type `Style` with target type `Button`)&mdash;Defines the **Cancel** button style.

The `DropDownSettings` also provides the following properties for dropdown customization:

* `Placement`(of type `PlacementMode`)&mdash;Specifies the position of the dropdown, can be set to Bottom, Right, Left, Top, Center or Relative.
* `HorizontalOffset` \ `VerticalOffset`&mdash;Specifies the horizontal\vertical distance between the dropdown and the TemplatedPicker.
* `IsFooterVisible`(`bool`)&mdash;Specifies whether the DropDown footer is currently visible. By default, the value is `True`.
* `AcceptButtonText`(`string`)&mdash;Defines the text visualized for the **Accept** button. By default, the text is `OK`.
* `CancelButtonText`(`string`)&mdash;Defines the text visualized for the **Cancel** button. By default, the text is `Cancel`.

## Example

The following example shows how the styling properties are applied.

**Define the `RadTemplatedPicker`**

<snippet id='templatedpicker-style' />

**Define the DropDownViewStyle**

<snippet id='dropDownViewStyle' />

**Define the FooterStyle**

<snippet id='timepicker-style-footer-style' />

**Define the AcceptButtonStyle**

<snippet id='timepicker-style-accept-button-style' />

**Define the CancelButtonStyle**

<snippet id='timepicker-style-cancel-button-style' />

## Namespaces

In addition, add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

The following image shows how the TemplatedPicker control looks when the styles described above are applied.

![TemplatedPicker DropDown Styling](../images/templatedpicker_dropdownstyle.png)

## See Also

- [TemplatedPicker Styling]({%slug templatedpicker-styling%})
