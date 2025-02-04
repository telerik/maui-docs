---
title: Templates
page_title: .NET MAUI ComboBox Documentation - Templates
description: Check our &quot;Templates&quot; documentation article for Telerik ComboBox for .NET MAUI control.
position: 11
slug: combobox-templates
---

# .NET MAUI ComboBox Templates

If the default templates of the control do not suit your needs, you can define custom ones. The available templates for customizing are:

* `ItemTemplate`(`DataTemplate`)&mdash;Defines the template of the items that are visualized in the dropdown list.
* `SelectedItemTemplate`(`DataTemplate`)&mdash;Defines the template of the selected items that are visualized in the dropdown list.
* `TokenTemplate`(`DataTemplate`)&mdash;Defines the template of the tokens that are visualized when multiple selection is performed.
* `ShowMoreTemplate`(`DataTemplate`)&mdash;Defines the Template of the Show More UI that gets visualized when the control is not focused and the space is not enough to show all tokens when using the Multiple selection mode.
* `SelectionBoxTemplate`(`DataTemplate`)&mdash;Defines the template of the selected item in the box section of the control. This property is only available when the `RadComboBox` is non-editable (`IsEditable` set to `false`).

> Use the `SelectionBoxTemplate` to customzie the content inside the input area when an item is selected, and the `DisplayMemberPath` property is not set. The `SelectionBoxTemplate` applies when the `SelectionMode` is `Single` and the control's `IsEditable` porperty is set to `false`.

### Example with ItemTemplate and SelectedItemTemplate

**1.** Define the [.NET MAUI ComboBox]({%slug combobox-overview%}) in XAML:

<snippet id='combobox-item-selecteditem-templates'/>

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Add a sample business model:

<snippet id='combobox-city-businessmodel'/>

**4.** Add the `ViewModel`:

<snippet id='combobox-cities-viewmodel'/>

The final result on WinUI: 

![.NET MAUI ComboBox Item and SelectedItem Templates](images/combobox-item-selecteditem-templates.png)

> For the ComboBox Item and SelectedItem Templates example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to ComboBox -> Templates category.

### Example with TokenTemplate and ShowMoreTemplate

**1.** Define the ComboBox in XAML:

<snippet id='combobox-tokentemplate'/>

**2.** Add a sample business model:

<snippet id='combobox-city-businessmodel'/>

**3.** Add the `ViewModel`:

<snippet id='combobox-cities-viewmodel'/>

> when the default TokenTemplate is overridden, you will need to implement custom logic for removing the tokens from the ComboBox:

Here is a sample logic removing the token when adding `TapGestureRecognizer` to the Label:

<snippet id='remove-the-selecteditem'/>

Here is the how the Token and ShowMore Templates look on WinUI:

![.NET MAUI ComboBox Token and Show More Templates](images/combobox-token-showmore-templates.png)

> For the ComboBox TokenTemplate and ShowMoreTemplate example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to ComboBox -> Templates category.

## See Also

- [Configuration]({%slug combobox-configuration%})
- [Header and Footer]({%slug combobox-header-footer%})
- [Edit Mode & Search]({%slug combobox-editmode-and-search%}) 
- [Single and Multiple Selection]({%slug combobox-selection%})
- [Styling]({%slug combobox-styling%})
