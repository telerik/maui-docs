---
title: Visual Structure
page_title: .NET MAUI DatePicker Documentation - Visual Structure
description: Learn what visual elements the Telerik DatePicker for .NET MAUI displays and see the visual structure of the control and its popup.
position: 2
previous_url: /controls/datepicker/datepicker-visual-structure
slug: datepicker-visual-structure
---

# .NET MAUI DatePicker Visual Structure

The DatePicker uses a set of visual elements when rendered.

## Displayed Elements

- `Placeholder`&mdash;The text that is visualized before picking a date. You can customize the placeholder through the [`PlaceholderTemplate`]({%slug datepicker-templates%}#placeholdertemplate) property.
- `DisplayStringFormat`&mdash;The text that is visualized after a date/time is picked.
- `Header`&mdash;The text that is displayed in the popup header. You can set it to a text input through the [`HeaderLabelText`]({%slug datepicker-styling%}#styling) property, or customize it by using the [`HeaderTemplate`]({%slug datepicker-templates%}#headertemplate) property.
- `SpinnerHeader`&mdash;The text that is visualized for the spinner header depending on the values that are picked. For example, if the `SpinnerFormatString` is `d`, the visualized text for the spinner header will be `Month` `Day` `Year`.
- `Spinner`&mdash;Displays items in a list.
- `SelectionHighlight`&mdash;Highlights the current selected date when the popup is open.
- `Footer`&mdash;The footer of the popup. By default, it contains the **OK** and **Cancel** buttons. You can customize it through the [`FooterTemplate`]({%slug datepicker-templates%}#footertemplate) property.

## DatePicker Structure

The following image shows the structure of the DatePicker before and after a date/time is selected.

![DatePicker Visual Structure](images/date_picker_placeholder_display.png "Visual elements of DatePicker control")

## Popup Structure

The following images show the visual structure of the DatePicker popup.

![DatePicker Popup Visual Structure](images/date_picker_structure.png "Visual elements of DatePicker Popup")

## See Also

- [.NET MAUI DatePicker Product Page](https://www.telerik.com/maui-ui/datepicker)
- [.NET MAUI DatePicker Forum Page](https://www.telerik.com/forums/maui?tagId=1853)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
