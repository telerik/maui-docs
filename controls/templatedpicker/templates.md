---
title: Templates
page_title: .NET MAUI TemplatedPicker Documentation - Templates
description: Check our &quot;Templates&quot; documentation article for Telerik TemplatedPicker for .NET MAUI control.
position: 3
previous_url: /controls/templatedpicker/templatedpicker-templates
slug: templatedpicker-templates
---

# Templates

The TemplatedPicker for .NET MAUI provides the following templates:

* `SelectorTemplate`(`ControlTemplate`)&mdash;Defines the template used for displaying the selector of the picker.

* `PlaceholderTemplate`(`ControlTemplate`)&mdash;Defines the template visualized for the placeholder.  

* `DisplayTemplate`(`ControlTemplate`)&mdash;Defines the template visualized when an item from the selector was picked.

When you use the `SelectorSettings` property (of type `Telerik.XamarinForms.Input.PickerPopupSelectorSettings`), you can define the following templates:

* `HeaderTemplate`(`ControlTemplate`)&mdash;Defines what will be displayed inside the dialog (popup) header.

* `FooterTemplate`(`ControlTemplate`)&mdash;Defines what will be displayed inside the dialog (popup) footer.

## Example

The following example demonstrates how to define the templates.

1. Define a sample TemplatedPicker:

 <snippet id='templatedpicker-keyfeatures' />

**Define the SelectorTemplate**

 <snippet id='templatedpicker-keyfeatures-selectortemplate' />

**Define the HeaderTemplate**

 <snippet id='templatedpicker-keyfeatures-headertemplate' />

1. Add the following data item for the first spinner:

 <snippet id='templatedpicker-country-businessmodel' />

1. Add the following data item for the second spinner:

 <snippet id='templatedpicker-city-businessmodel' />

1. Define a sample `ViewModel`:

 <snippet id='templatedpicker-viewmodel' />

1. Set the defined `LocationViewModel` as a `BindingContext` of the page:

 ```C#
this.BindingContext = new LocationViewModel();
 ```

1. In addition to this, you need to add the following namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```



The following image shows the TemplatedPicker visual structure:

![TemplatedPicker](images/templated_picker_visual_structure.png)

## See Also

- [Styling]({%slug templatedpicker-styling%})
