---
title: Configuration
page_title: .NET MAUI ComboBox Documentation - Configuration
description: Learn more about how to show the basic configuration options of the Telerik UI for .NET MAUI ComboBox control.
position: 2
slug: combobox-configuration
---

# Configure the .NET MAUI ComboBox

The purpose of this help article is to show the basic configuration options of the [.NET MAUI ComboBox]({%slug combobox-overview%}) control.

## Placeholder

* `Placeholder`(`string`): Sets the text which is used to give guidance to the end user on what can be entered/searched in the input. The watermark text is displayed when the input field is empty, or the selected item/s is/are cleared. 
* `PlaceholderColor`(`Color`): Defines the color for the watermark text. 

Here is an example of setting the `Placeholder` property:

<snippet id='combobox-configuration-placeholder'/>

The next image shows the result:

![ComboBox Placeholder](images/combobox-visual-structure.png)

Here is an example of setting the `PlaceholderColor` property:

<snippet id='combobox-configuration-placeholder-color'/>

The next image shows the result:

![.NET MAUI ComboBox Placeholder Color](images/combobox-placeholder-color.png)

## Text

* `Text`(`string`): Specifies the Text of the control. This is the Text that gets visualized when:
   * The control is editable.
   * The control is non-editable and the selection mode is single.

## Clear Button Visibility

The visibility state of the Clear **X** button can be changed using the `IsClearButtonVisible`(`bool`) property. By default its value is true.

Here is an example with `IsClearButtonVisible` property set:

<snippet id='combobox-configuration-clearbuttonvisible-false'/>

and the result: 

![ComboBox Clear Button Visibility](images/combobox-clearbuttonvisibility.png)

## Drop-Down Behavior

To manage the drop-down of the ComboBox, use the following properties:

* `DropDownWidth`(`double`)&mdash;Defines the width of the drop-down of the control.
* `DropDownHeight`(`double`)&mdash;Defines the height of the drop-down of the control.
* `DropDownVerticalOffset`(`double`)&mdash;Defines the vertical offset of the drop-down part of the control. This property allows an option to modify the control with no space between the ComboBox and the drop-down.
* `IsDropDownOpen`(`bool`)&mdash;Defines whether the drop-down part of the control is opened. The default value is `true`. 
* `IsDropdownClosedOnSelection`(`bool`)&mdash;Defines whether the drop-down will be closed when the item is selected or deselected. The default value is `true`.

Here is an example that uses the `DropDownWidth` property:

<snippet id='combobox-configuration-dropdownwidth'/>

Here is an example that uses the `DropDownHeight` property:

<snippet id='combobox-configuration-dropdownheight'/>

Here is an example that uses the `DropDownVerticalOffset` property:

<snippet id='combobox-configuration-dropdownverticaloffset'/>

Here is an example with `IsDropdownClosedOnSelection` property set:

<snippet id='combobox-configuration-dropdownvisibility-isdropdownclosed'/>

* `OpenOnFocus`(`bool`):Defines whether the drop down can be opened when the control is focused. The default value is `true`. The property is applicable for Editable ComboBox.

Here is an example with `OpenOnFocus` property set:

<snippet id='combobox-configuration-dropdownvisibility-openonfocus'/>

>tip Review the [Adding Select All Option in ComboBox Drop-Down]({%slug adding-select-all-option-combobox-dropdown-net-maui%}) article for more details how to select all items from the drop-down list.

## Keyboard

The `Keyboard` property of type `Microsoft.Maui.Keyboard` allows you to define the type of the keyboard that will be visualized by the device. The default value is Text.

>important The Configuration example can be found in our [SDK Browser Application]({%slug sdkbrowser-app%}). You can find the application in the **Examples** folder of your local **Telerik UI for .NET MAUI** installation or in the following [GitHub repo](https://github.com/telerik/maui-samples/tree/main/Samples/SdkBrowser).

## See Also

- [Data Binding]({%slug combobox-databinding%}) 
- [Edit Mode & Search]({%slug combobox-editmode-and-search%}) 
- [Selection]({%slug combobox-selection%}) 
