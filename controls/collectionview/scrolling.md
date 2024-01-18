---
title: Scrolling
page_title: .NET MAUI CollectionView Documentation - Scrolling
description: Try now the Telerik UI for .NET MAUI CollectionView Scrolling options like the Vertical Scrollbar and programmatic scrolling with the ScrollTo method.
position: 10
slug: collectionview-scrolling
tags: programmatic, scrolling, scrollbar
---

# .NET MAUI CollectionView Scrolling

The users can vertically scroll through the item in the CollectionView and also scroll to an item from the collection. 

## Scrolling to an Item

The CollectionView provides the `ScrollTo` method that allows you to programmatically scroll to an item in the CollectionView:

* `ScrollTo`(`object dataItem`)&mdash;Scrolls the visible area of the control so that the specified item is visible. The parameter is `dataItem`&mdash;Specifies the item to scroll to.

In addition to the `ScrollTo` method, the CollectionView exposes the `ScrollToCommand`that allows you to configure the control to display a specific item:

* `ScrollToCommand`(`ICommand`)&mdash;Gets a command that scrolls to an item in the control, which is specified as a parameter.

The following example demonstrates how to scroll to an item in the CollectionView control by using the `ScrollTo()` method.

**1.** Create a sample `DataModel`:

<snippet id='collectionview-datamodel' />

**2.** Define the `ViewModel` class:

<snippet id='collectionview-viewmodel' />

**3.** Define the `RadCollectionView` in XAML:

<snippet id='collectionview-programmatic-scrolling-xaml'/>

**4.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**5.** Button clicked event handler for calling the `ScrollTo` method:

<snippet id='collectionview-programmatic-scrolling'/>

> For a runnable demo with the CollectionView Programmatic Scrolling example, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **CollectionView > Scrolling** category.

## Vertical Scrolling

Configure the vertical scrollbar by using the following properties:

* `VerticalScrollBarVisibility` (enum of type `Microsoft.Maui.ScrollBarVisibility`)&mdash;Specifies the visibility of the vertical scrollbar. The available options are: 
	* `Default`&mdash;Applies the default visibility for the platform based on the content and orientation.
	* `Always`&mdash;The scrollbar is visible, regardless of the content or orientation.
	* `Never`&mdash;The scrollbar is not visible.


* `VerticalScrollBarLayoutMode` (enum of type `Telerik.Maui.Controls.ScrollBarLayoutMode`)&mdash;Specifies the layout mode of the vertical scrollbar. The available options are: 
	* `Overlay`&mdash;The scrollbars overlay the scrollable content when visible.
	* `Resize`&mdash;The scrollbars resize the scrollable content when visible.

### Example: Setting Vertical Scrollbar Visibility

The following example demonstrates how to manage the visibility of the vertical scrollbar.

**1.** Define the `RadCollectionView` in XAML:

<snippet id='collectionview-scrollbars'/>

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Create a sample `DataModel`:

<snippet id='collectionview-datamodel' />

**4.** Define the `ViewModel` class:

<snippet id='collectionview-viewmodel' />

> For a runnable demo with the CollectionView ScrollBars, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **CollectionView > Scrolling** category.

## Styling the Vertical ScrollBar

Apply styling to the vertical scrollbar by setting the `VerticalScrollBarStyle` property. The property is of type `Style` with a target type of `RadScrollBar.`

## See Also

- [Item Appearance]({%slug collectionview-item-appearance%})
- [Grouping]({%slug collectionview-grouping%})
- [Filtering]({%slug collectionview-filtering%})
- [Sorting]({%slug collectionview-sorting%})
- [Selection]({%slug collectionview-selection%})
- [Commands]({%slug collectionview-commands%})
- [Events]({%slug collectionview-commands%})

