---
title: Templates
page_title: .NET MAUI TimePicker Documentation | Templates
description: Check our &quot;Templates&quot; documentation article for Telerik TimePicker for .NET MAUI.
position: 3
previous_url: /controls/timepicker/timepicker-templates
slug: timepicker-templates
---

# Templates

In case the default templates of the TimePicker control do not suit your needs, you can easily define a custom template.

The available templates for customization are:

* `PlaceholderTemplate`(`ControlTemplate`)&mdash;Defines the template visualized for the placeholder.  
* `DisplayTemplate`(`ControlTemplate`)&mdash;Defines the template visualized when the picked time is displayed.
* `HeaderTemplate`(`ControlTemplate`)&mdash;Defines what will be displayed inside the dialog (popup) header.
* `FooterTemplate`(`ControlTemplate`)&mdash;Defines what will be displayed inside the dialog (popup) footer.

The example below shows a sample TimePicker definition with the listed above template properties applied:

1. Define the TimePicker.

 <snippet id='timepicker-custom-templates' />

1. Add the following namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

For the example, the template definitions are added to the page resources as follows.

## PlaceholderTemplate

<snippet id='timepicker-placeholder-template' />


![RadTimePicker PlaceholderTemplate](images/timepicker_placeholder_template.png)

## DisplayTemplate

<snippet id='timepicker-display-template' />

![RadTimePicker DisplayTemplate](images/timepicker_display_template.png)

## HeaderTemplate

<snippet id='timepicker-header-template' />

## FooterTemplate

<snippet id='timepicker-footer-template' />

![RadTimePicker FooterTemplate](images/timepicker_header_footer_template.png)


## See Also

- [Suppoted Standard Time Format Strings]({%slug timepicker-formatting%})
- [Styling]({%slug timepicker-styling%})
