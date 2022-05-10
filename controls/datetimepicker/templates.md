---
title: Templates
page_title: .NET MAUI DateTimePicker Documentation | Templates
description: Check our &quot;Templates&quot; documentation article for Telerik DateTimePicker for .NET MAUI.
position: 6
slug: datetimepicker-templates
---

# Templates

The DateTimePicker provides a set of templates for customizing its elements.

To customize the control, use any of the templates it supports:

* `PlaceholderTemplate`(`ControlTemplate`)&mdash;Defines the template visualized for the placeholder.  
* `DisplayTemplate`(`ControlTemplate`)&mdash;Defines the template visualized when the picked date/time is displayed.
* `HeaderTemplate`(`ControlTemplate`)&mdash;Defines what will be displayed inside the dialog (popup) header.
* `FooterTemplate`(`ControlTemplate`)&mdash;Defines what will be displayed inside the dialog (popup) footer.

## PlaceholderTemplate

The following example demonstrates how to use the `PlaceholderTemplate`.

<snippet id='datepicker-placeholder-default-template' />

## DisplayTemplate

The following example demonstrates how to use the `DisplayTemplate`.

<snippet id='datepicker-display-default-template' />

## HeaderTemplate

The following example demonstrates how to use the `HeaderTemplate`.

<snippet id='datepicker-header-default-template' />

## FooterTemplate

The following example demonstrates how to use the `FooterTemplate`.

<snippet id='datepicker-footer-default-template' />

Add the DateTimePicker definition:

```XAML
<telerik:RadDateTimePicker MinimumDate="2020,01,1"
							MaximumDate="2025,12,31"
							SpinnerFormat="MMM/dd/yyyy"
							PlaceholderTemplate="{StaticResource Picker_PlaceholderView_ControlTemplate}"
							DisplayTemplate="{StaticResource Picker_DisplayView_ControlTemplate}">
	<telerik:RadDateTimePicker.SelectorSettings>
		<telerik:PickerPopupSelectorSettings HeaderTemplate="{StaticResource PopupView_Header_ControlTemplate}"
												  HeaderLabelText="Date Picker"
												  FooterTemplate="{StaticResource PopupView_Footer_ControlTemplate}"/>
	</telerik:RadDateTimePicker.SelectorSettings>
</telerik:RadDateTimePicker>
```

## Customization Examples

The snippet below shows a simple Date Picker definition:

<snippet id='datepicker-custom-templates' />

Now, let's add the templates definition to the page resources:

**Define Custom PlaceholderTemplate**

<snippet id='datepicker-placeholder-template' />

![DateTimePicker PlaceholderTemplate](images/datepicker_placeholder_template.png)

**Define Custom DisplayTemplate**

<snippet id='datepicker-display-template' />

![DateTimePicker DisplayTemplate](images/datepicker_display_template.png)

**Define Custom HeaderTemplate**

<snippet id='datepicker-header-template' />

**Define Custom FooterTemplate**

<snippet id='datepicker-footer-template' />

In addition to this, you need to add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

![DateTimePicker FooterTemplate](images/datepicker_header_footer_template.png)

## See Also

- [Formatting]({%slug datetimepicker-formatting%})
- [Date Range]({%slug datetimepicker-date-range%})
- [Styling]({%slug datetimepicker-styling%})
