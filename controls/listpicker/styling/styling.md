---
title: Styling
page_title: .NET MAUI  ListPicker Documentation | Styling
description: Check our &quot;Styling&quot; documentation article for Telerik ListPicker for .NET MAUI.
position: 8
slug: listpicker-styling
---

# Styling

The ListPicker control for .NET MAUI provides styling options for customizing its appearance.

## ListPicker Styling

ListPicker for .NET MAUI provides the following Style properties for customizing its look:

* `ItemStyle`(of type `Style` with target type `telerikDataControls:SpinnerItemView`)&mdash;Defines the style applied to the list of items.
* `SelectedItemStyle`(of type `Style` with target type `telerikDataControls:SpinnerItemView`)&mdash;Defines the style applied to the selected item.
* `SelectionHighlightStyle`(of type `Style` with target type `telerik:RadBorder`)&mdash;Specifies the style applied to the border where the current selection is.  
* `PlaceholderLabelStyle`(of type `Style` with target type `Label`)&mdash;Defines the style applied to the placeholder label.
* `DisplayLabelStyle`(of type `Style` with target type `Label`)&mdash;Defines the style applied to the label which is visualized when item of the list is selected.

`PickerContentView` class exposes the following properties for styling the ListPicker border and background color:

* `BackgroundColor`&mdash;Defines the background color of the picker.
* `BorderColor`&mdash;Defines the border color of the picker.
* `BorderThickness`&mdash;Specifies the border thickness of the picker. The default value is `new Thickness(0,0,0,1)`.
* `CornerRadius`&mdash;Specifies the corner radius of the picker.

## Popup Styling

By using the `SelectorSettings` property (of type `Telerik.XamarinForms.Input.PickerPopupSelectorSettings`) of the ListPicker you can modify the appearance of the dialog (popup). `PickerPopupSelectorSettings` class exposes the following Style properties:

* `PopupViewStyle`(of type `Style` with target type `telerikInput:PickerPopupContentView`)&mdash;Defines the popup view style.
* `HeaderStyle` (of type `Style` with target type `telerikInput:PickerPopupHeaderView`)&mdash;Defines the popup header style.
* `HeaderLabelStyle`(of type `Style` with target type `Label`)&mdash;Defines the popup header label style.
* `FooterStyle`(of type `Style` with target type `telerikInput:PickerPopupFooterView`)&mdash;Defines the popup footer style.
* `AcceptButtonStyle`(of type `Style` with target type `Button`)&mdash;Defines the **Accept** button style.
* `CancelButtonStyle`(of type `Style` with target type `Button`)&mdash;Defines the **Cancel** button style.

The `SelectorSettings` also provides the following properties for popup customization:

* `PopupOutsideBackgroundColor`&mdash;Defines the color outside of the popup.
* `IsPopupModal`(`bool`)&mdash;Defines a Boolean value indicating if the popup should be closed when tapped outside of the popup. By default the value of the `IsPopupModal` is `false`.
	* When `IsPopupModal="True"`  the UI behind the popup gets inactive and cannot be used until the popup is closed.
	* When `IsPopupModal="False"` the popup could be closed when clicking outside the popup.

* `HeaderLabelText`(`string`)&mdash;Specifies the text visualized in the popup header. The default text is `Select Item`.
* `IsHeaderVisible`(`bool`)&mdash;Specifies whether the Popup header is currently visible. By default, the value is `True`.
* `IsFooterVisible`(`bool`)&mdash;Specifies whether the Popup footer is currently visible. By default, the value is `True`.
* `AcceptButtonText`(`string`)&mdash;Defines the text visualized for the accept button. By default, the text is `OK`.
* `CancelButtonText`(`string`)&mdash;Defines the text visualized for the cancel button. By default, the text is `Cancel`.

## Namespaces

Using `ItemStyle`, `SelectedItemStyle` you need to add the following namespace:

```XAML
xmlns:telerikDataControls="clr-namespace:Telerik.XamarinForms.DataControls;assembly=Telerik.Maui.Controls.Compatibility"
```

Using `PopupViewStyle`, `HeaderStyle`, `FooterStyle` add the following namespace:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

`SelectionHighlightStyle` requires the following namespace:

```XAML
xmlns:telerikPrimitives="clr-namespace:Telerik.XamarinForms.Primitives;assembly=Telerik.Maui.Controls.Compatibility"
```

## Styling Examples

The following examples show how the styling properties are applied.

1. Define the ListPicker:

<snippet id='listpicker-features-styling' />

Define the styles in the page resources:

**Define the itemstyle**

<snippet id='listpicker-features-itemstyle' />

**Define the SelectedItem Style**

<snippet id='listpicker-features-selecteditemstyle' />

**Define the PlaceholderLabel Style**

<snippet id='listpicker-style-placeholder-label-style' />

**Define the DisplayLabel Style**

<snippet id='listpicker-style-display-label-style' />

1. Define a sample business model:

 <snippet id='listpicker-features-businessmodel' />

1. Set a `ViewModel`:

 <snippet id='listpicker-features-viewmodel' />

1. Add the following namespaces:

 ```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
xmlns:telerikDataControls="clr-namespace:Telerik.XamarinForms.DataControls;assembly=Telerik.Maui.Controls.Compatibility"
 ```

The following image shows how the ListPicker looks when the styling properties are applied:

![ListPicker Styling](../images/listpicker_styling.png)

>important For a sample styling example, refer to the **ListPicker/Styling** folder of the [Telerik UI for .NET MAUI SDKBrowser Application]({%slug maui-demo-app%}).

## See Also

- [Popup Styling]({%slug listpicker-popup-styling%})
- [DropDown Styling]({%slug listpicker-dropdown-styling%})
- [Looping]({%slug listpicker-looping%})
- [Templates]({%slug listpicker-templates%})
