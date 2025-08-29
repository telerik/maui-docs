---
title: DropDown Styling
page_title: .NET MAUI ListPicker Documentation - DropDown Styling
description: "Apply the styling options of the Telerik UI for .NET MAUI ListPicker DropDown"
position: 3
slug: listpicker-dropdown-styling
---

# .NET MAUI ListPicker DropDown Styling

By using the `DropDownSettings` property (of type `Telerik.Maui.controls.PickerDropDownSettings`) of the ListPicker, you can modify the appearance of the dropdown. The `PickerDropDownSettings` class exposes the following `Style` properties:

* `DropDownViewStyle`(of type `Style` with target type `telerik:PickerDropDownContentView`)&mdash;Defines the dropdown view style.
* `FooterStyle`(of type `Style` with target type `telerik:PickerPopupFooterView`)&mdash;Defines the dropdown footer style.
* `AcceptButtonStyle`(of type `Style` with target type `Button`)&mdash;Defines the **Accept** button style.
* `CancelButtonStyle`(of type `Style` with target type `Button`)&mdash;Defines the **Cancel** button style.

The `DropDownSettings` also provides the following properties for dropdown customization:

* `Placement`(of type `PlacementMode`)&mdash;Specifies the position of the dropdown, can be set to Bottom, Right, Left, Top, Center or Relative.
* `HorizontalOffset` \ `VerticalOffset`&mdash;Specifies the horizontal\vertical distance between the dropdown and the ListPicker.
* `IsFooterVisible`(`bool`)&mdash;Specifies whether the DropDown footer is currently visible. By default, the value is `True`.
* `AcceptButtonText`(`string`)&mdash;Defines the text visualized for the **Accept** button. By default, the text is `OK`.
* `CancelButtonText`(`string`)&mdash;Defines the text visualized for the **Cancel** button. By default, the text is `Cancel`.

## Styling Examples

The following examples demonstrate how to define use the styling properties of the ListPicker.

**Define the `RadListPicker`**

<snippet id='listpicker-dropdown-style' />

**Define the DropDownViewStyle**

<snippet id='listpicker-style-dropdownview-style' />

**Define the FooterStyle**

<snippet id='listpicker-style-footer-style' />

**Define the AcceptButtonStyle**

<snippet id='listpicker-style-accept-button-style' />

**Define the CancelButtonStyle**

<snippet id='listpicker-style-cancel-button-style' />


In addition, add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"                      
```

The following image shows what the ListPicker control looks like when the styles described above are applied:

![ListPicker DropDown Style](../images/listpicker_dropdownstyle.png)

## See Also

- [ListPicker Styling]({%slug listpicker-styling%})
