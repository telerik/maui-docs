---
title: Item Style
page_title: .NET MAUI TreeView Documentation - Item Style
description: "Review how to style the checkboxes, expand indicator, item of the TreeView for .NET MAUI."
position: 1
slug: treeview-item-style
---

# Stlying the items in the TreeView

This article explains how to style the elements in the TreeView control. 

## Styling the Treeview

Style the TreeView by using the following properties:

* `BackgroundColor`(`Color`)&mdash;Specifies the background color of the control.
* `BorderColor`(`Color`)&mdash;Specifies the border color of the control.
* `BorderBrush`(`Color`)&mdash;Specifies the border brush of the control.
* `BorderThickness`(`Thickness`)&mdash;Specifies the border thickness of the control.
* `CornerRadius`(`Thickness`)&mdash;Specifies the corner radius of the control.
* `ContentPadding`(`Thickness`)&mdash;Specifies the content padding of the control.

## Styling and configuring the TreeView Item

The TreeView provides styling mechanism for customizing the look of its items.
To utilize it set the `ItemStyle` property of the control(with target type `TreeViewItemView`).

The available properties are:

* `IsExpanded`(`bool`)&mdash;Defines a value indicating whether the tree item is expanded.
* `IsChecked`(`bool?`)&mdash;Defines a value indicating whether the tree item is checked.
* `ImageSource`(`ImageSource`)&mdash;Defines the source of the image to display in the tree item.
* `IsImageVisible`(`bool`)&mdash;Defines a value indicating whether the image is visible.
* `IsExpandButtonVisible`(`bool`)&mdash;Defines a value indicating whether the expand button is visible.
* `BackgroundColor`(`Color`)&mdash;Defines the spacing in pixels between the elements of the tree item.
* `BorderBrush`(`Brush`)&mdash;Defines the spacing in pixels between the elements of the tree item.
* `BorderThickness`(`Thickness`)&mdash;Defines the spacing in pixels between the elements of the tree item.
* `TextColor`(`Color`)&mdash;Defines the spacing in pixels between the elements of the tree item.

Define the style in tha resources of the page: 

<snippet id='treeview-item-styling'/>

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

## Styling the expand button

Style the expand button(which is used for expanding/collapsing the TreeView item) by using the `TreeViewItemExpandButton`. It inherits from the `TreeViewItemButton`. The control used for the button is the Telerik `RadButton` cotnrol. All stying properties available for [RadButton]({%slug button-overview%}) can be applied to `TreeViewItemExpandButton`.

<snippet id='treeview-expand-styling'/>

## Styling the image

Style the image in the TreeView item by using the `TreeViewItemImage`. The control used for this image is the .NET MAUI `Image` control.

<snippet id='treeview-image-styling'/>

## Style the checkbox

Style the checkbox element in the TreeView by using the `TreeViewItemCheckBox`:

<snippet id='treeview-item-checkbox-styling'/>

The control used for the Checkbox elements is the [Telerik RadCheckBox control]({%slug checkbox-overview%}). You can use all styling proeprties RadCheckBox provides to style the checkbox elements in the TreeView.

>important For the Treeview ItemStyle example refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) TreeView -> Styling category.

## See Also

* [Expand/Collapse]({%slug treeview-expand-collapse%})
* [CheckBoxes]({%slug treeview-checkboxes%})
* [Scrolling]({%slug treeview-scrolling%})
* [Selection]({%slug treeview-selection%})
* [Events]({%slug treeview-events%})
* [Commands]({%slug treeview-commands%})