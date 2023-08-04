---
title: Templates
page_title: .NET MAUI TimePicker Documentation - Templates
description: Learn more about the templates in the Telerik UI for .NET MAUI TimePicker control.
position: 3
previous_url: /controls/timepicker/timepicker-templates
slug: timepicker-templates
---

# .NET MAUI TimePicker Templates

In case the default templates of the TimePicker control do not suit your needs, you can define a custom template.

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

## Placeholder Template

<snippet id='timepicker-placeholder-template' />


![TimePicker Placeholder Template](images/timepicker_placeholder_template.png)

## Display Template

<snippet id='timepicker-display-template' />

![TimePicker Display Template](images/timepicker_display_template.png)

## Header Template

<snippet id='timepicker-header-template' />

## Footer Template

<snippet id='timepicker-footer-template' />

![TimePicker Footer Template](images/timepicker_header_footer_template.png)


## See Also

- [Supported Standard Time Format Strings]({%slug timepicker-formatting%})
- [Styling]({%slug timepicker-styling%})
