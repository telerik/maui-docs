---
title: Templates
page_title: .NET MAUI DatePicker Templates
description: Learn how to customize the Telerik UI for .NET MAUI DatePicker with placeholder, display, header, and footer templates in your app.
components: ["datepicker"]
position: 7
previous_url: /controls/datepicker/datepicker-templates
slug: datepicker-templates
---

# Customize DatePicker Templates in .NET MAUI

Use the Telerik UI for .NET MAUI DatePicker templates to customize the placeholder area, selected date display, and the popup header and footer. This article helps you choose the correct template for each part of the control and shows how to apply them together.

## Choosing a DatePicker Template

Use the following templates to customize specific parts of the DatePicker:

| Template | Type | Use It When |
|---|---|---|
| `PlaceholderTemplate` | `ControlTemplate` | You want to change what the control shows before the user picks a date. |
| `DisplayTemplate` | `ControlTemplate` | You want to customize how the selected date appears in the input area. |
| `HeaderTemplate` | `ControlTemplate` | You want to customize the popup header through `PopupSettings` for popup `PickerMode`, or `DropDownSettings` for dropdown `PickerMode`. |
| `FooterTemplate` | `ControlTemplate` | You want to customize the popup footer through `PopupSettings` for popup `PickerMode`, or `DropDownSettings` for dropdown `PickerMode`. |

## PlaceholderTemplate

Use `PlaceholderTemplate` when you want to replace the default placeholder content before the user selects a date.

The following example shows how to use the default `PlaceholderTemplate`:

<snippet id='datepicker-placeholder-default-template' />

## DisplayTemplate

Use `DisplayTemplate` when you want to change how the selected date is rendered after the user picks a value.

The following example shows how to use the default `DisplayTemplate`:

<snippet id='datepicker-display-default-template' />

## HeaderTemplate

Use `HeaderTemplate` when you want to customize the popup header area.

The following example shows how to use the default `HeaderTemplate`:

<snippet id='datepicker-header-default-template' />

## FooterTemplate

Use `FooterTemplate` when you want to customize the popup footer area.

The following example shows how to use the default `FooterTemplate`:

<snippet id='datepicker-footer-default-template' />

## Example with Default Templates

After you define the templates in your page resources, assign them to the DatePicker and its selector settings:

```XAML
<telerik:RadDatePicker MinimumDate="2020,1,1"
					   MaximumDate="2025,12,31"
					   DisplayTemplate="{StaticResource Picker_DisplayView_ControlTemplate}"
					   PlaceholderTemplate="{StaticResource Picker_PlaceholderView_ControlTemplate}">
	<telerik:RadDatePicker.SelectorSettings>
		<telerik:PickerPopupSelectorSettings HeaderTemplate="{StaticResource PopupView_Header_ControlTemplate}"
										   HeaderLabelText="Date Picker"
										   FooterTemplate="{StaticResource PopupView_Footer_ControlTemplate}" />
	</telerik:RadDatePicker.SelectorSettings>
</telerik:RadDatePicker>
```

## Customization Example

Declare the `telerik` namespace before adding the DatePicker and its templates:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

Define a simple DatePicker:

<snippet id='datepicker-custom-templates' />

Add the templates to the page resources.

### Define a Custom PlaceholderTemplate

<snippet id='datepicker-placeholder-template' />

The following image shows a DatePicker with the custom placeholder template:

![DatePicker displaying a custom placeholder template](images/datepicker_placeholder_template.png)

### Define a Custom DisplayTemplate

<snippet id='datepicker-display-template' />

The following image shows a DatePicker with the custom display template:

![DatePicker displaying a custom display template](images/datepicker_display_template.png)

### Define a Custom HeaderTemplate

<snippet id='datepicker-header-template' />

### Define a Custom FooterTemplate

<snippet id='datepicker-footer-template' />

The `HeaderTemplate` and `FooterTemplate` apply to the popup configured through `PickerPopupSelectorSettings`.

The following image shows the customized popup header and footer templates:

![DatePicker popup displaying custom header and footer templates](images/datepicker_header_footer_template.png)

## See Also

* [DatePicker Visual Structure]({%slug datepicker-visual-structure%})
* [DatePicker Picker Mode]({%slug datepicker-picker-mode%})
* [Formatting the Telerik UI for .NET MAUI DatePicker]({%slug datepicker-formatting%})
* [.NET MAUI DatePicker Styling]({%slug datepicker-styling%})
* [.NET MAUI DatePicker Product Page](https://www.telerik.com/maui-ui/datepicker)
