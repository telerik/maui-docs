---
title: Group Header
page_title: .NET MAUI CollectionView Documentation - Group Templates
description: Check the Telerik UI for .NET MAUI CollectionView GroupHeader's BindingContext properties and how to define a custom GroupHeaderTemplate.
position: 4
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

The `CollectionViewGroupFHeaderItemView` exposes the following properties listed in the table below: 



## Customizing the Group Header

If the default look how the group header is presented do not match your use case, you can define custom templates by setting the `GroupHeaderTemplate` property.

**1.** Define the `GroupHeaderTemplate`:

**1.** Set the template to the `RadCollectionView`:

## See Also


