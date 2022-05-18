---
title: Templates
page_title: .NET MAUI ComboBox Documentation | Templates
description: Check our &quot;Templates&quot; documentation article for Telerik ComboBox for .NET MAUI control.
position: 9
slug: combobox-templates
---

# Templates

If the default templates of the control do not suit your needs, you can easily define custom ones. The available templates for customizing are:

* `ItemTemplate`(`DataTemplate`): Defines the template of the items that are visualized in the dropdown list.

> When the selection mode is single and the control is not editable if there is ItemTemplate set the same template will be visualized in the box part of the control when item is selected.

* `SelectedItemTemplate`(`DataTemplate`): Defines the template of the selected items that are visualized in the dropdown list.
* `TokenTemplate`(`DataTemplate`): Defines the template of the tokens that are visualized when multiple selection is performed.
* `ShowMoreTemplate`(`DataTemplate`): Defines the Template of the show more UI that gets visualized when the control is not focused and there is not enough space for all Tokens to be visualized when the selection mode is multiple.

### Example with ItemTemplate and SelectedItemTemplate

Here is the ComboBox definition in XAML:

<snippet id='combobox-item-selecteditem-templates'/>

you need to add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

the sample business model

<snippet id='combobox-city-businessmodel'/>

and the ViewModel used:

<snippet id='combobox-cities-viewmodel'/>

The final result: 

![ComboBox Item and selectedItem Templates](images/combobox-item-selecteditem-templates.png)

>important The Item and SelectedItem Template example can be found in our [SDK Browser Application]({%slug sdkbrowser-app%}). You can find the applications in the **Examples** folder of your local **Telerik UI for .NET MAUI** installation or in the following [GitHub repo](https://github.com/telerik/maui-samples/tree/main/Samples/SdkBrowser).

### Example with TokenTemplate and ShowMoreTemplate

Here is the ComboBox definition in XAML:

<snippet id='combobox-tokentemplate'/>

Add the sample business model

<snippet id='combobox-city-businessmodel'/>

and the ViewModel used:

<snippet id='combobox-cities-viewmodel'/>

> when the default TokenTemplate is overridden, you will need to implement custom logic for removing the tokens from the ComboBox:

here is a sample logic removing the token when adding TapGestureRecognizer to the Label:

<snippet id='remove-the-selecteditem'/>

Here is the how the Token and ShowMore Templates look:

![ComboBox Token and Show More Templates](images/combobox-token-showmore-templates.png)

>important The Token and ShowMore Template example can be found in our [SDK Browser Application]({%slug sdkbrowser-app%}). You can find the applications in the **Examples** folder of your local **Telerik UI for .NET MAUI** installation or in the following [GitHub repo](https://github.com/telerik/maui-samples/tree/main/Samples/SdkBrowser).

## See Also

- [Configuration]({%slug combobox-configuration%})
- [Header and Footer]({%slug combobox-header-footer%})
- [Edit Mode & Search]({%slug combobox-editmode-and-search%}) 
- [Single and Multiple Selection]({%slug combobox-selection%})
- [Styling]({%slug combobox-styling%})
