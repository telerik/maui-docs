---
title: Improving CollectionView Performance in .NET MAUI
description: Tips and tricks for optimizing the performance of the CollectionView when dealing with large datasets and ideal layout practices.
type: how-to
page_title: Enhancing Performance for .NET MAUI CollectionView with Large Datasets
meta_title: Enhancing Performance for .NET MAUI CollectionView with Large Datasets
slug: improve-collectionview-performance-dotnet-maui
tags: collectionview, .net maui, performance, layouts, images, optimization, loadondemand, paging
res_type: kb
---

## Environment

| Product | Author | 
| --- | ---- | 
| Telerik UI for .NET MAUI CollectionView | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I need tips and best practices to optimize performance when using the CollectionView control with thousands of data entries. I want to know how layouts wrapping the control affect performance and whether images reduce performance.

This knowledge base article also answers the following questions:
- How to optimize performance for CollectionView with large datasets?
- What are layout best practices for CollectionView in .NET MAUI?
- Do images in CollectionView affect performance?

## Solution

To optimize the performance of the CollectionView in .NET MAUI, follow these steps:
* [Avoid Nesting in ScrollView or StackLayout](#avoid-nesting-in-scrollview-or-stacklayout)
* [Configure Uniform Item Sizes](#configure-uniform-item-sizes)
* [Implement Load-on-Demand or Paging](#implement-load-on-demand-or-paging)
* [Optimize Image Handling](#optimize-image-handling)

### Avoid Nesting in ScrollView or StackLayout

Position the CollectionView inside a `Grid` with a `*` row height. Avoid nesting the control inside `Stack` or `ScrollView`. Nesting scrollable objects breaks UI virtualization and can impact performance. Refer to [Microsoft documentation](https://learn.microsoft.com/en-us/dotnet/maui/user-interface/controls/scrollview?view=net-maui-10.0) for details on scrollable objects.

Avoid wrapping Telerik MAUI TreeView, DataGrid, TreeDataGrid, RichTextEditor, or PDF Viewer controls in a ScrollView. These controls have internal scrolling.

### Configure Uniform Item Sizes

Telerik `RadCollectionView` does not expose an `ItemSizingStrategy` property. That property and its `MeasureFirstItem` option belong to the Microsoft .NET MAUI `CollectionView` API.

For uniform items, set `ItemLength` on a `CollectionViewLinearLayout` through `RadCollectionView.ItemsLayout`. In a vertical layout, `ItemLength` specifies the item height. In a horizontal layout, it specifies the item width.

With the `telerik` prefix mapped to `http://schemas.telerik.com/2022/xaml/maui`, add the following property element inside your existing `RadCollectionView` to configure 75-unit-high rows:

```XAML
<telerik:RadCollectionView.ItemsLayout>
	<telerik:CollectionViewLinearLayout ItemLength="75" />
</telerik:RadCollectionView.ItemsLayout>
```

Choose a length that fits your item template, including its padding. For more configuration options, see [CollectionView Linear Layout]({%slug collectionview-linear-layout%}).

`ItemLength` controls item size. It does not instruct the control to measure only the first item or guarantee faster scrolling.

To support pull-to-refresh, you can keep `RadCollectionView` inside a `RefreshView`, as shown in [CollectionView Refresh Data]({%slug collectionview-pull-to-refresh%}). Place the `RefreshView` in a bounded layout, such as a `Grid` row with `*` height. A `RefreshView` wrapper alone does not establish the cause of scrolling lag.

### Implement Load-on-Demand or Paging

Load large datasets incrementally using the [LoadOnDemand](https://www.telerik.com/maui-ui/documentation/controls/collectionview/load-on-demand/overview) feature or divide them into manageable chunks with the [Paging](https://www.telerik.com/maui-ui/documentation/controls/collectionview/paging) feature.

### Optimize Image Handling

When working with images, implementing caching strategies is a way to optimize the image loading process. For more details, refer to this [image loading tutorial](https://www.youtube.com/watch?v=sDtx5ORYrmw&ab_channel=GeraldVersluis).

## See Also

- [CollectionView Overview](https://www.telerik.com/maui-ui/documentation/controls/collectionview/overview)
- [CollectionView Load On Demand](https://www.telerik.com/maui-ui/documentation/controls/collectionview/load-on-demand/overview)
- [CollectionView Paging](https://www.telerik.com/maui-ui/documentation/controls/collectionview/paging)
- [Image Loading Strategies](https://www.youtube.com/watch?v=sDtx5ORYrmw&ab_channel=GeraldVersluis)