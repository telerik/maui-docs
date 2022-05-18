---
title: Header and Footer
page_title: .NET MAUI ComboBox Documentation | Templates
description: Check our &quot;Header and Footer&quot; documentation article for Telerik ComboBox for .NET MAUI control.
position: 9
slug: combobox-header-footer
---

# Header and Footer 

You can easily add Header and Footer to the DropDown list of the ComboBox control through the following properties:

* `HeaderTemplate`(`DataTemplate`): Defines the template of the header that will be visualized in the drop down list.
* `FooterTemplate`(`DataTemplate`): Defines the template of the footer that will be visualized in the drop down list.

> It is not recommended to add controls in the Header and Footer which steal the focus (like Entry, editor, etc.) from the ComboBox control, as unexpected behavior may occur. 

## Example 

Here is the ComboBox definition in XAML:

<snippet id='combobox-header-footer-template'/>

the sample business model

<snippet id='combobox-city-businessmodel'/>

and the ViewModel used:

<snippet id='combobox-cities-viewmodel'/>

This is how the Header and Footer Templates look: 

![ComboBox Header Footer Templates](images/combobox-header-footer.png)

>important Header and Footer Template example can be found in our [SDK Browser Application]({%slug sdkbrowser-app%}). You can find the applications in the **Examples** folder of your local **Telerik UI for .NET MAUI** installation or in the following [GitHub repo](https://github.com/telerik/maui-samples/tree/main/Samples/SdkBrowser).

## See Also

- [Configuration]({%slug combobox-configuration%})
- [Header and Footer]({%slug combobox-header-footer%})
- [Edit Mode & Search]({%slug combobox-editmode-and-search%}) 
- [Single and Multiple Selection]({%slug combobox-selection%})
- [Styling]({%slug combobox-styling%})