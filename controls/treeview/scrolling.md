---
title: Scrolling
page_title: .NET MAUI TreeView Documentation - Scrolling
description: "Review te scrolling mechanism TreeView for .NET MAUI provides."
position: 6
slug: treeview-scrolling
---

# Scrolling

You can easily scroll in the Treeview in both directions&mdash;Horizontally and verticaly or coose only one direction. 

## Scrollbars

Treeview provides vertical and horizontal scrolling through its items.

### Vertical scrolling

Configure the vertical scrollbar by using the following properties:

* `VerticalScrollBarVisibility`(enum of type `Microsoft.Maui.ScrollBarVisibility`)&mdash;Specifies the visibility of the vertical scroll bar.
The available options are: 
	* `Default`&mdash;The visibility of the scrollbar will be the default for the platform based on the content and orientation.
	* `Always`&mdash;The scollbar is visible, regardless of the content or orientation.
	* `Never`&mdash;The scrollbar is not visible.


* `VerticalScrollBarLayoutMode`(enum of type `Telerik.Maui.controls.ScrollBarLayoutMode`)&mdash;Specifies the layout mode of the vertical scroll bar.
The available options are: 
	* `Overlay`&mdash;The scroll bars overlay the scrollable content when visible.
	* `Resize`&mdash;The scroll bars resize the scrollable content when visible.

### Horizontal scrolling

Configure the horizontal scrollbar by using the following properties:

* `HorizontalScrollBarVisibility`(enum of type `Microsoft.Maui.ScrollBarVisibility`)&mdash;Specifies the visibility of the horizontal scroll bar.
The available options are: 
	* `Default`&mdash;The visibility of the scrollbar will be the default for the platform based on the content and orientation.
	* `Always`&mdash;The scollbar is visible, regardless of the content or orientation.
	* `Never`&mdash;The scrollbar is not visible.

* `HorizontalScrollBarLayoutMode`(enum of type `Telerik.Maui.controls.ScrollBarLayoutMode`)&mdash;Specifies the layout mode of the horizontal scroll bar. 
The available options are: 
	* `Overlay`&mdash;The scroll bars overlay the scrollable content when visible.
	* `Resize`&mdash;The scroll bars resize the scrollable content when visible.

### Example

RadTreeView definiton:

<snippet id='treeview-scrolling'/>

The Location data model:

<snippet id='treeview-location-model'/>

The Country data model:

<snippet id='treeview-country-model'/>

The City data model:

<snippet id='treeview-city-model'/>

The ViewModel:

<snippet id='treeview-location-viewmodel'/>

## Methods 

* `ScrollTo`(`object dataItem`)&mdash;Scrolls the visible area of the control so that the specified item is visible. The parameter is `dataItem`&mdash;Specifies the item to scroll to.

RadTreeview definition: 

<snippet id='treeview-programmatic-scrolling-xaml'/>

ScrollTo executon on button click:

<snippet id='treeview-programmatic-scrolling'/>

The Location data model:

<snippet id='treeview-location-model'/>

The Country data model:

<snippet id='treeview-country-model'/>

The City data model:

<snippet id='treeview-city-model'/>

The ViewModel:

<snippet id='treeview-location-viewmodel'/>

## Commands

* `ScrollToCommand`(`ICommand`)&mdash;Gets a command that scrolls to an item in the control, which is specified as a parameter.

>important For the Treeview Scrolling examples refer to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) TreeView -> Scrolling category.

## See Also

* [Expand/Collapse]({%slug treeview-expand-collapse%})
* [CheckBoxes]({%slug treeview-checkboxes%})
* [Styling]({%slug treeview-item-style%})
* [Selection]({%slug treeview-selection%})
* [Events]({%slug treeview-events%})
* [Commands]({%slug treeview-commands%})
