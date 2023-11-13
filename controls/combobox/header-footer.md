---
title: Header and Footer
page_title: .NET MAUI ComboBox Documentation - Templates
description: Learn more about the header and footer templates to the dropdown list of Telerik UI For .NET MAUI ComboBox control.
position: 10
slug: combobox-header-footer
---

# Header and Footer in .NET MAUI ComboBox

You can add Header and Footer to the DropDown list of the ComboBox control through the following properties:

* `HeaderTemplate`(`DataTemplate`)&mdash;Defines the template of the header that will be visualized in the drop down list.
* `FooterTemplate`(`DataTemplate`)&mdash;Defines the template of the footer that will be visualized in the drop down list.

> It's not recommended to add controls in the Header and Footer which steal the focus (like Entry, editor, etc.) from the ComboBox control, as unexpected behavior may occur. 

## Example 

Here is the ComboBox definition in XAML:

<snippet id='combobox-header-footer-template'/>

the sample business model

<snippet id='combobox-city-businessmodel'/>

and the ViewModel used:

<snippet id='combobox-cities-viewmodel'/>

This is how the Header and Footer Templates look: 

![ComboBox Header Footer Templates](images/combobox-header-footer.png)

> For the ComboBox Header and Footer example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to ComboBox -> Templates category.

## See Also

- [Configuration]({%slug combobox-configuration%})
- [Header and Footer]({%slug combobox-header-footer%})
- [Edit Mode & Search]({%slug combobox-editmode-and-search%}) 
- [Single and Multiple Selection]({%slug combobox-selection%})
- [Styling]({%slug combobox-styling%})
