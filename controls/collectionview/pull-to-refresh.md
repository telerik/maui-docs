---
title: Pull to Refresh
page_title: .NET MAUI CollectionView Documentation - Pull-to-Refresh
description: Learn how to achieve pull to refresh functionality in the Telerik UI for .NET MAUI CollectionView.
position: 13
slug: collectionview-pull-to-refresh
tags: refreshview, .net maui, maui, collectionview, pull to refresh
---

# .NET MAUI CollectionView Pull to Refresh

Some lists contain items that may change after the initial load. The _pull-to-refresh_ functionality allows the user to manually trigger an update of the list.

You can achieve pull to refresh functionality in Telerik .NET MAUI CollectionView by using the <a href="https://learn.microsoft.com/en-us/dotnet/maui/user-interface/controls/refreshview?view=net-maui-8.0" target="_blank">Microsoft .NET MAUI `RefreshView`</a>.

## Example 

The following example demonstrates how to use the .NET MAUI `RefresView` with `RadCollectionView`.

**1.** Define the `RefreshView` and `RadCollectionView` in XAML:

<snippet id='collectionview-pull-to-refresh-xaml'/>

**2.** Add the following namespaces:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Define sample business model:

<snippet id='collectionview-grouptapcommand-model'/>

**4.** Add the `ViewModel`:

<snippet id='collectionview-pull-to-refresh'/>

This is the result on Android:

![.NET MAUI CollectionView Pull To Refresh](images/collectionview-pull-to-refresh.gif)

## See Also

- [Grouping]({%slug collectionview-grouping%})
- [Filtering]({%slug collectionview-filtering%})
- [Selection]({%slug collectionview-selection%})
- [Commands]({%slug collectionview-commands%})