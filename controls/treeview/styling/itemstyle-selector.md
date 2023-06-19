---
title: ItemStyle Selector
page_title: .NET MAUI TreeView Documentation - ItemStyle Selector
description: The TreeView exposes a conditional styling feature that allows you to apply different styles to each item depending on a specific condition.
position: 2
slug: treeview-itemstyle-selector
---

# Style Selector on Items

The .NET MAUI TreeView exposes a conditional styling feature that allows you to apply different styles to each item depending on a specific condition.

![.NET MAUI TreeView Item Style Selector](images/treeview-itemstyle-selector.png)

The following example shows how to use the `ItemStyleSelector`:

**1.** Set the `ItemStyleSelector` property to the `RadTreeView`:

<snippet id='treeview-item-styleselector'/>

**2.** Define the style selector in XAML:

<snippet id='treeview-style-selector'/>

**3.** Add the custom `LocationStyleSelector` class that inherits from `IStyleSelector`:

<snippet id='treeview-styleselector'/>

**4.** Set the style to the `RadTreeView`:

<snippet id='treeview-styling'/>

**5.** Add the location data model:

<snippet id='treeview-location-model'/>

**6.** Add the country data model:

<snippet id='treeview-country-model'/>

**7.** Add the city data model:

<snippet id='treeview-city-model'/>

**8.** Add the ViewModel:

<snippet id='treeview-location-viewmodel'/>

> For a runnable example demonstrating the TreeView ItemStyleSelector, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **TreeView > Styling**.

## See Also

* [Expand and Collapse TreeView Items]({%slug treeview-expand-collapse%})
* [CheckBoxes in TreeView]({%slug treeview-checkboxes%})
* [Styling the TreeView Item]({%slug treeview-item-style%})
* [Scrolling options]({%slug treeview-scrolling%})
* [Multiple and Single Selection]({%slug treeview-selection%})
* [Events]({%slug treeview-events%})
* [Available Commands in .NET MAUI TreeView]({%slug treeview-commands%})