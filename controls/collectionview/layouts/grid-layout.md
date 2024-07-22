---
title: Grid Layout
page_title: .NET MAUI CollectionView Documentation - Grid Layout
description: Learn how to configure the CollectionView to display the items vertically or horizontally.
position: 1
slug: collectionview-grid-layout
tags: .net maui, collectionview, layout, grid layout
---

# .NET MAUI CollectionView Grid Layout

The CollectionView control supports grid layout through its `ItemsLayout` property. The `ItemsLayout` accepts values of type `CollectionViewLayoutBase` which is a base class.


The grid layout allows distributing cells in a fixed number of columns/rows. The grid layout can be set by creating an instance of the `CollectionViewGridLayout` class and assigning it to the `RadCollectionView.ItemsLayout` property.

Sample `RadCollectionView` definition with `CollectionViewGridLayout`:

```XAML
<telerik:RadCollectionView>
    <telerik:RadCollectionView.ItemsLayout>
        <telerik:CollectionViewGridLayout />
    </telerik:RadCollectionView.ItemsLayout>
</telerik:RadCollectionView>
```

This is how the items are arranged when grid layout is defined:

![.NET MAUI CollectionView Grid Layout](../images/collectionview-grid-layout.png "Telerik .NET MAUI CollectionView")

The properties available in the `CollectionViewGridLayout` are: 

* `SpanCount` (`int`)&mdash;Specifies the count of the columns or rows (depending on the orientation) of the layout.The value must be `>= 1`. The default value is `2`.
* `HorizontalItemSpacing` (`double`)&mdash;Specifies the horizontal empty space around each item. The default value is `0.0`.
* `VerticalItemSpacing` (`double`)&mdash;Specifies the vertical empty space around each item.The default value is `0.0`.
* `Orientation` (enum or type `Telerik.Maui.Orientation`)&mdash;Specifies the orientation of the layout. The available options are: `Horizontal` and (default) `Vertical`.

## Example with Grid Layout

The following example demonstrates how to apply grid layout to the `RadCollectionView`.
 
**1.** Define the following business object:

<snippet id='collectionview-datamodel' />

**2.** Create a `ViewModel` class as shown below:

<snippet id='collectionview-viewmodel' />

**3.** Add the `RadCollectionView` definition with grid layout:

<snippet id='collectionview-grid-layout' />

**4.** Include the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" 
```

This is the result:

![.NET MAUI CollectionView Grid Layout](../images/collectionview-grid-layout-configuration.png "Telerik .NET MAUI CollectionView")

> For a runnable demo with the CollectionView `CollectionViewGridLayout`, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **CollectionView > Layouts** category.

## See Also

- [Grouping]({%slug collectionview-grouping%})
- [Sorting]({%slug collectionview-sorting%})
- [Selection]({%slug collectionview-selection%})
- [Commands]({%slug collectionview-commands%})