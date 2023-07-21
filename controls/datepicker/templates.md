---
title: Templates
page_title: .NET MAUI DatePicker Documentation - Templates
description: Learn more about the templates in the Telerik UI for .NET MAUI DatePicker control.
position: 7
previous_url: /controls/datepicker/datepicker-templates
slug: datepicker-templates
---

# .NET MAUI DatePicker Templates

The Telerik UI for .NET MAUI DatePicker provides a set of templates for customizing its elements.

## Placeholder Template

The `PlaceholderTemplate`(`ControlTemplate`) defines the template visualized for the placeholder of the DatePicker. The following example demonstrates how to set the default placeholder template.

<snippet id='datepicker-placeholder-default-template' />

You can also customize the placeholder template.

1. Define the DatePicker:

 <snippet id='datepicker-custom-templates' />

1. Define the template.

	<snippet id='datepicker-placeholder-template' />

1. Add the following namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

The following image shows the end result.

![DatePicker PlaceholderTemplate](images/datepicker_placeholder_template.png)

## Display Template

The `DisplayTemplate`(`ControlTemplate`) defines the template visualized when the picked date/time of the DatePicker is displayed. The following example demonstrates how to set the display template.

<snippet id='datepicker-display-default-template' />

You can also customize the display template.

1. Define the DatePicker:

 <snippet id='datepicker-display-template' />

1. Define the template.

	<snippet id='datepicker-placeholder-template' />

1. Add the following namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

The following image shows the end result.

![DatePicker DisplayTemplate](images/datepicker_display_template.png)

## Header Template

The `HeaderTemplate`(`ControlTemplate`) defines what will be displayed inside the dialog (popup) header of the DatePicker. The following example demonstrates how to set the header template.

<snippet id='datepicker-header-default-template' />

You can also customize the header template.

1. Define the DatePicker:

 <snippet id='datepicker-display-template' />

1. Define the template.

 <snippet id='datepicker-header-template' />

1. Add the following namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

## Footer Template

The `FooterTemplate`(`ControlTemplate`) defines what will be displayed inside the dialog (popup) footer of the DatePicker. The following example demonstrates how to set the footer template.

<snippet id='datepicker-footer-default-template' />

You can also customize the footer template.

1. Define the DatePicker:

 <snippet id='datepicker-display-template' />

1. Define the template.

 <snippet id='datepicker-footer-template' />

1. Add the following namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

The following image shows the end result.

![DatePicker FooterTemplate](images/datepicker_header_footer_template.png)


## See Also

- [Formatting the Telerik UI for .NET MAUI DatePicker]({%slug datepicker-formatting%})
- [.NET MAUI DatePicker Styling]({%slug datepicker-styling%})
- [.NET MAUI DatePicker Product Page](https://www.telerik.com/maui-ui/datepicker)
