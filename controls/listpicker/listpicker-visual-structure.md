---
title: Visual Structure
page_title: .NET MAUI List Picker Documentation | ListPicker Visual Structure
description: Check our &quot;Visual Structure&quot; documentation article for Telerik ListPicker for .NET MAUI.
position: 0
slug: listpicker-visual-structure
---

# Visual Structure

Here are described all visual elements used in the List Picker for .NET MAUI.

## List Picker Structure before and after an item is selected

![ListPicker Visual Structure](images/listpicker_structure_placeholder_display.png "Visual elements of ListPicker control")

## ListPicker Popup Visual Structure

![ListPicker Visual Structure Popup](images/listpicker_structure.png "Visual elements of List Picker Popup")

## Legend

- **Placeholder** - the text visualized before picking an item from the list of items. Placeholder could be customized through the [PlaceholderTemplate]({%slug listpicker-templates%}#placeholder-template) property.
- **DisplayStringFormat** - the text vislualized after an item from the list of items is picked.
- **Header** - the text displayed in the popup header. It could be set a direct text through the [HeaderLabelText]({%slug listpicker-templates%}) property or fully customize the popup header using the [HeaderTemplate]({%slug listpicker-templates%}#header-template) property
- **ItemTemplate**  - Defines the template used for displaying the list of items. For more information review [Templates]({%slug listpicker-templates%}) article. 
- **SelectedItemTemplate** - Specifies the template used for visualizing the selected item from the list. For more information review [Templates]({%slug listpicker-templates%}) article. 
- **Footer** - the footer of the popup. By default is contains OK and Cancel Buttons. It could be customized through the FooterTemplate property. For more information review [Templates]({%slug listpicker-templates%}) article. 