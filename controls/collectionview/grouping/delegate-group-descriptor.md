---
title: Delegate Group Descriptor
page_title: .NET MAUI CollectionView Documentation - Delegate Group Descriptor
description: Review the Telerik UI for .NET MAUI CollectionView DelegateGroupDescriptor option which enables you to group by a custom key.
position: 2
slug: collectionview-delegate-group-descriptor
tags: group, collectionview, groupdescriptor, dotnet maui, maui, grouping items
---

# .NET MAUI CollectionView Delegate Group Descriptor

The `CollectionViewDelegateGroupDescriptor` enables you to group by a custom key (for example, some complex expression combining two or more properties) instead of being limited by the value of a single property. This descriptor exposes the following properties:

- `KeyExtractor`&mdash;Defines the `(Func<object, object)` delegate which returns the property to retrieve the group key for each data item.
- `SortOrder`(enum of type `Telerik.Maui.Controls.CollectionView.CollectionViewSortOrder`)&mdash;Specifies the sort order of the grouped items. The available options are: `Ascending` or `Descending`.

Let's use the same example from the previous section, and add `CollectionViewDelegateGroupDescriptor` through code instead.



> For a runnable demo with the CollectionView DelegateGroupDescriptor example, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **Calendar > Grouping** category.

## See Also

