---
title: Visual Structure
page_title: .NET MAUI TimeSpanPicker Documentation - Visual Structure
description: Learn what visual elements the Telerik TimeSpanPicker for .NET MAUI displays, and explore the visual structure of the control.
position: 0
previous_url: /controls/timespanpicker/timespanpicker-visual-structure
slug: timespanpicker-visual-structure
---

# .NET MAUI TimeSpanPicker Visual Structure

The visual structure of the .NET MAUI TimeSpanPicker represents the anatomy of the UI control. Being familiar with the visual elements of the TimeSpanPicker allows you to quickly find the information required to configure them.

The images in this article show the anatomy of the TimeSpanPicker and its building blocks.

## TimeSpanPicker Structure

![TimeSpanPicker Visual Structure](images/timespan_picker_placeholder_display.png "Visual elements of TimeSpan Picker control")

- **Placeholder**&mdash;The text visualized before the user picks a date/time. You can customize the placeholder through the [`PlaceholderTemplate`]({%slug timespanpicker-templates%}#placeholdertemplate) property.
- **Display String Format**&mdash;The text visualized after a date/time is picked.

## Popup Visual Structure

>note Currently, the TimeSpanPicker does not provide spinners for milliseconds.

![TimeSpanPicker Popup Visual Structure](images/timespan_picker_structure.png "Visual elements of TimeSpan Picker Popup")

- `Header` and `HeaderLabelText`&mdash;The text displayed in the popup header. You can set it to a direct text input through the [`HeaderLabelText`]({%slug timespanpicker-styling%}) property or customize the popup header by using the [`HeaderTemplate`]({%slug timespanpicker-templates%}#headertemplate) property.
- `SpinnersHeader`&mdash;The text visualized for the spinner header depending on the values that will be picked. For example, if the `SpinnerFormat` is `g`, the text visualized for the spinner header will be **Days** **Hours** **Minutes** **Seconds**.
- `Spinner`&mdash;Displays time interval values in a list.
- `SelectionHighlight`&mdash;Highlights the currently selected time interval when the popup is open.
- `Footer`&mdash;The footer of the popup. By default, it contains the **OK** and **Cancel** buttons. You can customize it through the [`FooterTemplate`]({%slug timespanpicker-templates%}#footertemplate) property.

## See Also

- [Templates]({%slug timespanpicker-templates%})
- [Commands]({%slug timespanpicker-commands%})
