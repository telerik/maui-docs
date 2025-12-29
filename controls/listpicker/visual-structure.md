---
title: Visual Structure
page_title: .NET MAUI ListPicker Documentation - Visual Structure
description: Learn what visual elements are displayed by the Telerik UI for .NET MAUI ListPicker, and see how these elements build the visual structure of the control.
position: 0
previous_url: /controls/listpicker/listpicker-visual-structure
slug: listpicker-visual-structure
---

# .NET MAUI ListPicker Visual Structure

The visual structure of the .NET MAUI ListPicker represents the anatomy of the UI control. Being familiar with the visual elements of the ListPicker allows you to quickly find the information required to configure them.

The images in this article show the anatomy of the ListPicker and its building blocks.

## ListPicker Structure

![ListPicker Visual Structure](images/listpicker_structure_placeholder_display.png "Visual elements of ListPicker control")

- **Placeholder**&mdash;The text visualized before picking an item from the list of items. A placeholder can be customized through the [`PlaceholderTemplate`]({%slug listpicker-templates%}#placeholder-template) property.

## Popup Visual Structure

![ListPicker Visual Structure Popup](images/listpicker_structure.png "Visual elements of List Picker Popup")

- **Header**&mdash;The text displayed in the popup header. You can set a direct text through the [`HeaderLabelText`]({%slug listpicker-templates%}) property or customize the popup header by using the [`HeaderTemplate`]({%slug listpicker-templates%}#header-template) property.
- **ItemTemplate**&mdash;Defines the template used for displaying the list of items. For more information review [Templates]({%slug listpicker-templates%}) article.
- **SelectedItemTemplate**&mdash;Specifies the template used for visualizing the selected item from the list. For more information review the [Templates]({%slug listpicker-templates%}) article.
- **Footer**&mdash;The footer of the popup. By default, it contains the **OK** and **Cancel** buttons. You can customize it through the `FooterTemplate` property. For more information, review the [Templates]({%slug listpicker-templates%}) article.
