---
title: Group View
page_title: .NET MAUI CollectionView Documentation - Group View
description: Check the Telerik UI for .NET MAUI CollectionView GroupView's BindingContext properties and how to define a custom GroupHeaderTemplate.
position: 1
slug: collectionview-group-header
tags: group, collectionview, groupdescriptor, custom group header
---

# .NET MAUI CollectionView Group Header

The CollectionView has a default group header that is displayed when grouping is applied.

The `BindingContext` of the `GroupHeader` is a complex object&mdash;`GroupContext` and includes the following properties:

- `IsExpanded`&mdash;Defines a value indicating whether the group is currently expanded (has its child items visible).
- `Items`&mdash;Gets the child items of the group.
- `Key`&mdash;Gets the specific for the group key.
- `Level`&mdash;Gets the zero-based level (or the depth) of the group.

## Styling the Group View

The CollectionView control for .NET MAUI provides the following styling properties for customizing the appearance of the group view:

* `GroupViewStyle`(`Style` with target type `RadCollectionViewGroupView`)&mdash;Specifies the style applied to the group view.
* `GroupViewStyleSelector`(`Style` with target type `RadCollectionViewGroupView`)&mdash;Specifies the style selector for the group view.

## Customizing the Area With the Group Header Text

You can customize the default look of the group area where the text is displayed by setting the `GroupHeaderTemplate` (`DataTemplate`) property.

The following example demonstrates how to customize the group.

**1.** Define the following business object:

<snippet id='collectionview-datamodel' />

**2.** Create a `ViewModel` class as shown below:

<snippet id='collectionview-viewmodel' />

**3.** Add the `RadCollectionView` definition with `GroupHeaderTemplate`:

<snippet id='collectionview-group-header-template' />

**4.** Include the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" 
```

> For a runnable demo with the CollectionView `GroupHeaderTemplate`, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **CollectionView > Grouping** category.

## See Also

- [Property Group Descriptor]({%slug collectionview-property-group-descriptor%})
- [Multi-level Grouping Descriptor]({%slug collectionview-grouping-multilevel%})