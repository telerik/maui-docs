---
title: Group Header
page_title: .NET MAUI CollectionView Documentation - Group Templates
description: Check the Telerik UI for .NET MAUI CollectionView GroupHeader's BindingContext properties and how to define a custom GroupHeaderTemplate.
position: 3
slug: collectionview-group-header
tags: group, collectionview, groupdescriptor, custom group header
---

# .NET MAUI CollectionView Group Header

The CollectionView has a default group header that is displayed when grouping is applied.

The `BindingContext` of the `GroupHeader` is a complex object and it includes the following properties:

- `IsExpanded`&mdash;Defines a value indicating whether the group is currently expanded (has its child items visible).
- `Items`&mdash;Gets the child items of the group.
- `Key`&mdash;Gets the specific for the group key.
- `Level`&mdash;Gets the zero-based level (or the depth) of the group.

## Styling the Group Header

The CollectionView control for .NET MAUI provides the following styling properties for customizing the appearance of its header:

* `GroupHeaderStyle`(`Style` with target type `CollectionViewGroupHeaderItemView`)&mdash;Specifies the style applied to the group header.
* `GroupHeaderStyleSelector`(`Style` with target type `CollectionViewGroupFHeaderItemView`)&mdash;Specifies the style selector for the group header.

## Customizing the Group Header

You can change the default look of the group header so that it matches your use case and style. To achieve this, define custom templates by setting the `GroupHeaderTemplate` property.

The following example demonstrates how to customize the group header by using the `GroupHeaderTemplate`.

**1.** Define the following business object:

<snippet id='collectionview-datamodel' />

**2.** Create a `ViewModel` class as shown below:

<snippet id='collectionview-viewmodel' />

**3.** Add the `RadCollectionView` definition with `GroupHeaderTemplate`:

<snippet id='collectionview-group-header-footer' />

**4.** Include the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" 
```

> For a runnable demo with the CollectionView GroupHeaderTemplate, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **Calendar > Grouping** category.

## See Also

- [Property Group Descriptor]({%slug collectionview-property-group-descriptor%})
- [Bindable Group Descriptors]({%slug collectionview-bindable-group-descriptor%})
- [Multi-level Grouping Descriptor]({%slug collectionview-grouping-multilevel%})
- [Group Footer]({%slug collectionview-group-footer%})
