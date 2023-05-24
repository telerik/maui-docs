---
title: Scrolling
page_title: .NET MAUI TreeView Documentation - Scrolling
description: "Review te scrolling mechanism TreeView for .NET MAUI provides."
position: 6
slug: treeview-scrolling
---

# Scrolling

You can easily scroll in the Treeview in both directions&mdash;horizontally and verticaly or coose only one direction. 

## Horizontal scrolling

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


## Vertical scrolling

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

## Methods 

* `ScrollTo`(`object dataItem`)&mdash;Scrolls the visible area of the control so that the specified item is visible. The parameter is `dataItem`&mdash;Specifies the item to scroll to.

## Commands

* `ScrollToCommand`(`ICommand`)&mdash;Gets a command that scrolls to an item in the control, which is specified as a parameter.

## Example

Here is a sample definition of the TreeView control:

<snippet id='treeview-scrolling-xaml'/>

Inside ScrollItemIntoViewClicked event handler get the concrete item you'd need to navigate to and call **ScrollItemIntoView** method of the TreeView:

<snippet id='treeview-programmaticscrolling-code'/>
	
And the end result:

#### Figure 1: Scrolling item into View

![](images/treeview_scrolling.png)

>important You can check a runnable demo in the **Features** section of the **RadTreeView** component in the **SDK Samples Browser application**(can be found in the Examples folder of your local *Telerik UI for Xamarin* installation)

## See Also

* [Expand/Collapse]({%slug treeview-expand-collapse-api%})
* [Commands]({%slug treeview-commands%})
