---
title: Data Binding
page_title: .NET MAUI CollectionView Documentation - Data Binding
description: Learn what are the options for data binding in Telerik UI CollectionView for .NET MAUI control.
position: 2
slug: collectionview-data-binding
---

# .NET MAUI CollectionView Data Binding

For all cases where the business items are not simple strings, data-binding is necessary to correctly visualize information. The CollectionView for .NET MAUI component supports data binding in the form of path property.

## Populate with Data

- `ItemsSource` (`object`)&mdash;Defines the collection of the items that will populate the control with data.
- `DisplayMemberPath` (`string`)&mdash;Defines the name of the property which will be visualized inside the CollectionView.

> If DisplayMemberPath is not set the “ToString” implementation of the business object will be visualized. The DisplayMemberPath is a property that helps the developers to visualize an exact property from the business object they are bound to.

## Define Item Appearance

The CollectionView provides a default appearance of the items. If you want to customize this appearance, define an `ItemTemplate` (`DataTemplate`).

Here is an exmaple with `ItemTemplate`:

**1.** Create a sample model:

<snippet id='collectionview-grouptapcommand-model' />

**2.** Create a `ViewModel`:

<snippet id='collectionview-grouptapcommand-viewmodel' />

**3.** Define the CollectionView control with a sample `ItemTemplate`:

<snippet id='commectionview-grouptapcommand' />

**4.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```	

## Item Appearance at Runtime

When the CollectionView is bound to a collection of multiple data item objects and the appearance of each item depends on a specific property of the business object then you can define an item appearance at runtime by setting the `RadCollectionView.ItemTemplate` property to a `DataTemplateSelector` object.

# See Also
