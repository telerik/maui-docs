---
title: Scrolling
page_title: .NET MAUI CollectionView Documentation - Scrolling
description: Try now the Telerik UI for .NET MAUI CollectionView Scrolling options like the Vertical Scrollbar and programmatic scrolling with the ScrollTo method.
position: 10
slug: collectionview-scrolling
tags: programmatic, scrolling, scrollbar
---

# .NET MAUI CollectionView Scrolling

You can enable users to scroll in the CollectionView in both directions&mdash;horizontally and vertically and also scroll to an item from the collection. 

## Scrolling to an item

The CollectionView provides the `ScrollTo` method that allows you to configure the control to display a specific item:

* `ScrollTo`(`object dataItem`)&mdash;Scrolls the visible area of the control so that the specified item is visible. The parameter is `dataItem`&mdash;Specifies the item to scroll to.

In addition to the `ScrollTo` method, the CollectionView exposes the `ScrollToCommand`that allows you to configure the control to display a specific item:

* `ScrollToCommand`(`ICommand`)&mdash;Gets a command that scrolls to an item in the control, which is specified as a parameter.

## Vertical Scrolling

Configure the vertical scrollbar by using the following properties:

* `VerticalScrollBarVisibility` (enum of type `Microsoft.Maui.ScrollBarVisibility`)&mdash;Specifies the visibility of the vertical scrollbar. The available options are: 
	* `Default`&mdash;Applies the default visibility for the platform based on the content and orientation.
	* `Always`&mdash;The scrollbar is visible, regardless of the content or orientation.
	* `Never`&mdash;The scrollbar is not visible.


* `VerticalScrollBarLayoutMode` (enum of type `Telerik.Maui.Controls.ScrollBarLayoutMode`)&mdash;Specifies the layout mode of the vertical scrollbar. The available options are: 
	* `Overlay`&mdash;The scrollbars overlay the scrollable content when visible.
	* `Resize`&mdash;The scrollbars resize the scrollable content when visible.

### Styling the Vertical ScrollBar

Apply styling to the vertical scrollbar by setting the `VerticalScrollBarStyle` property. The porperty is of type `Style` with a target type of `RadScrollBar.`

## Horizontal Scrolling

Configure the horizontal scrollbar by using the following properties:

* `HorizontalScrollBarVisibility` (enum of type `Microsoft.Maui.ScrollBarVisibility`)&mdash;Specifies the visibility of the horizontal scrollbar.
The available options are: 
	* `Default`&mdash;Applies the default visibility for the platform based on the content and orientation.
	* `Always`&mdash;The scrollbar is visible, regardless of the content or orientation.
	* `Never`&mdash;The scrollbar is not visible.

* `HorizontalScrollBarLayoutMode` (enum of type `Telerik.Maui.Controls.ItemsView.ScrollBarLayoutMode`)&mdash;Specifies the layout mode of the horizontal scrollbar. 
The available options are: 
	* `Overlay`&mdash;The scrollbars overlay the scrollable content when visible.
	* `Resize`&mdash;The scrollbars resize the scrollable content when visible.

### Styling the Horizontal ScrollBar

Apply styling to the horizontal scrollbar by setting the `HorizontalScrollBarStyle` property. The porperty is of type `Style` with a target type of `RadScrollBar.`

## See Also


