---
title: Empty Template
page_title: .NET MAUI CollectionView Documentation - Empty Template
description: Learn more about the Empty Template property of the .NET MAUI CollectionView control.
position: 17
slug: collectionview-empty-template
---

# .NET MAUI CollectionView Empty Template

The CollectionView allows you to specify a template that the control will use when the `ItemsSource` is null or the collection is empty. In this way, you notify the user that no data is available to display.

CollectionView exposes the following properties:

* `EmptyStyle`(`Style` with target type `ItemsEmptyView`)&mdash;Specifies the style applied to the empty content when the control contains no data.
* `EmptyTemplate`(`DataTemplate`)&mdash;Defines the content of the view which is shown when in the CollectionView has no items.

## Example: Defining the EmptyTemplate in the CollectionView

**1.** Define the `RadCollectionView` in XAML:

<snippet id='collectionview-empty-template'/>

**2.** Define the `Style` for the `EmptyTemplate`:

<snippet id='collectionview-empty-style'/>

**3.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**4.** Create a sample `DataModel`:

<snippet id='collectionview-datamodel' />

**5.** Define the `ViewModel` class:

<snippet id='collectionview-viewmodel' />

> For a runnable example demonstrating the CollectionView EmptyTemplate, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **CollectionView > EmptyTemplate** category.

## See Also

- [Grouping]({%slug collectionview-grouping%})
- [Filtering]({%slug collectionview-filtering%})
- [Selection]({%slug collectionview-selection%})
- [Commands]({%slug collectionview-commands%})