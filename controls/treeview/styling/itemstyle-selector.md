---
title: ItemStyle Selector
page_title: .NET MAUI TreeView Documentation - ItemStyle Selector
description: "Style the TreeView for .NET MAUI items by using a style selector."
position: 2
slug: treeview-itemstyle-selector
---

# Style Selector on Items

The TreeView exposes conditional styling feature. It allows users to apply a different Style to each item depending on a specific condition.

![.NET MAUI TreeView Item Style Selector](images/treeview-itemstyle-selector.png)

**Example**

The `ItemStyleSelector` property set to the RaDTreeView:

<snippet id='treeview-item-styleselector'/>

The Style Selector defined in XAML:

<snippet id='treeview-style-selector'/>

The custom class `LocationStyleSelector` that inherits from `IStyleSelector`:

<snippet id='treeview-styleselector'/>

Set the style to the `RadTreeView`:

<snippet id='treeview-styling'/>

The Location data model:

<snippet id='treeview-location-model'/>

The Country data model:

<snippet id='treeview-country-model'/>

The City data model:

<snippet id='treeview-city-model'/>

The ViewModel:

<snippet id='treeview-location-viewmodel'/>

>important For the Treeview ItemStyle Selector example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) TreeView -> Styling category

## See Also

* [Expand/Collapse]({%slug treeview-expand-collapse%})
* [CheckBoxes]({%slug treeview-checkboxes%})
* [Styling]({%slug treeview-item-style%})
* [Scrolling]({%slug treeview-scrolling%})
* [Selection]({%slug treeview-selection%})
* [Events]({%slug treeview-events%})
* [Commands]({%slug treeview-commands%})