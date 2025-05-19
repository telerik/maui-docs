---
title: Sticky Group Headers
page_title: .NET MAUI CollectionView Documentation - Sticky Group Grouping
description: Review the Telerik UI for .NET MAUI CollectionView Sticky Group Headers option which if enabled makes the GroupHeader freeze while scrolling through the items until the whole group is scrolled away.
position: 6
slug: collectionview-sticky-group-header
tags: group, collectionview, groupdescriptor, sticky, group, headers
---

# .NET MAUI CollectionView Sticky Group Headers (Android and iOS)

The CollectionView for .NET MAUI provides the option to set its group headers as sticky (only on Android and iOS). This means the `GroupHeader` UI element "freezes" while scrolling through the items until the whole group is scrolled away. As you scroll through the next group, the currently stuck group header will be pushed by the next group header.

In a multi-level grouping scenario, the last inner group from the parent group will be sticky.

To enable the sticky group headers behavior, set `EnableStickyGroupHeaders` (`bool`) property of the CollectionView to `True`. By default, the `EnableStickyGroupHeaders` value is `False`.

```XAML
<telerik:RadCollectionView EnableStickyGroupHeaders="True"  />
```
```C#
var collectionView = new RadCollectionView();
collectionView.EnableStickyGroupHeaders = true;
```

Here is how the sticky group headers look in a single-level grouping scenario:

![.NET MAUI CollectionView Sticky Group Headers](../images/collectionview-sticky-group-header.gif)

Here is how the sticky group headers look in multi-level grouping scenario:

![.NET MAUI CollectionView Sticky Group Headers Multi-Level Grouping](../images/collectionview-sticky-group-multi-level.gif)

## See Also

- [Property Group Descriptor]({%slug collectionview-property-group-descriptor%})
- [Delegate Group Descriptor]({%slug collectionview-delegate-group-descriptor%})
- [Multi-level Grouping Descriptor]({%slug collectionview-grouping-multilevel%})
- [Group Header]({%slug collectionview-group-header%})
