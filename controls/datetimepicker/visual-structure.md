---
title: Visual Structure
page_title: .NET MAUI DateTimePicker Documentation - Visual Structure
description: "Learn what visual elements the Telerik DateTimePicker for .NET MAUI displays and see the visual structure of the control and its popup."
position: 0
slug: datetimepicker-visual-structure
---

# .NET MAUI DateTimePicker Visual Structure

The DateTimePicker uses a set of visual elements when rendered.

## Displayed Elements

- **Placeholder**&mdash;The text that is visualized before picking a date/time. You can customize the placeholder through the [`PlaceholderTemplate`]({%slug datetimepicker-templates%}#placeholdertemplate) property.
- **DisplayStringFormat**&mdash;The text that is visualized after a date/time is picked.
- **Header**&mdash;The text that is displayed in the popup header. You can set it to a text input through the [`HeaderLabelText`]({%slug datetimepicker-styling%}#styling) property, or fully customize it by using the [`HeaderTemplate`]({%slug datetimepicker-templates%}#headertemplate) property.
- **SpinnerHeader**&mdash;The text that is visualized for the spinner header depending on the values that are picked. For example, if the `SpinnerFormatString` is `d`, and `AreSpinnerHeadersVisible` property is set to `True` the visualized text for the spinner header will be **Month** **Day** **Year**.
- **Spinner**&mdash;Displays items in a list.
- **SelectionHighlight**&mdash;Highlights the current selected date when the popup is open.
- **Footer**&mdash;The footer of the popup. By default, it contains the **OK** and **Cancel** buttons. You can customize it through the [`FooterTemplate`]({%slug datetimepicker-templates%}#footertemplate) property.

## DateTimePicker Structure

The following image shows the structure of the DateTimePicker before and after a date/time is selected.

![DateTimePicker Visual Structure](images/datetime_picker_placeholder_display.png "Visual elements of DateTimePicker control")

## Popup Structure

The following images show the visual structure of the DateTimePicker popup.

![DateTimePicker Popup Visual Structure](images/datetime_picker_structure.png "Visual elements of DateTimePicker Popup")

## DropDown Structure

The following images show the visual structure of the DateTimePicker dropdown.

![DateTimePicker Popup Visual Structure](images/datetime_picker_structure.png "Visual elements of DateTimePicker Popup")