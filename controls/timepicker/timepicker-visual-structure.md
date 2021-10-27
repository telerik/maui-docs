---
title: Visual Structure
page_title: .NET MAUI TimePicker Documentation | Time Picker Visual Structure
description: Check our &quot;Visual Structure&quot; documentation article for Telerik TimePicker for .NET MAUI.
position: 0
slug: timepicker-visual-structure
---

# Visual Structure

Here are described all visual elements used in the TimePicker for .NET MAUI.

## Time Picker Structure before and after a time value is selected

![Time Picker Visual Structure](images/time_picker_placeholder_display.png "Visual elements of Time Picker control")

## Picker Popup Visual Structure

![Time Picker Popup Visual Structure](images/time_picker_structure.png "Visual elements of Time Picker Popup")

## Legend ##

- **Placeholder** - the text visualized before picking a time value. Placeholder can be customized through the [PlaceholderTemplate]({%slug timepicker-templates%}#placeholdertemplate) property.
- **DisplayStringFormat** - the text visualized after a time value is picked.
- **Header** - the text displayed in the popup header. It can be set to a direct text through the [HeaderLabelText]({%slug timepicker-styling%}#popup-styling) property or fully customize the popup header using the [HeaderTemplate]({%slug timepicker-templates%}#headertemplate) property.
- **SpinnerHeader** - the text visualized for spinner header depending on the values to be picked. For example if the `SpinnerFormatString` is *g* and `AreSpinnerHeadersVisible="True"` The text visualized for spinner header will be **Hour** **Minutes** **AM/PM**.
- **Spinner** - displays items in a list.
- **SelectionHighlight** - highlight the currently selected time when the popup is open.
- **Footer** - the footer of the popup. By default is contains OK and Cancel Buttons. It can be customized through the [FooterTemplate]({%slug timepicker-templates%}#footertemplate) property.

## See Also

- [Getting Started]({%slug timepicker-getting-started%})
- [Time Format Strings]({%slug timepicker-formatting%})