---
title: Multi-Level Grouping
page_title: .NET MAUI CollectionView Documentation - Grouping
description: Review the Telerik UI for .NET MAUI CollectionView Multi-Level Grouping feature and how to enable it. 
position: 5
slug: collectionview-grouping-multilevel
tags: group, collectionview, groupdescriptor, multilevel, nested grouping, maui, dotnet maui
---

# .NET MAUI CollectionView Multi-Level Grouping

This article provides an overview on how you can enable multi-level grouping in the CollectionView.

Create the following business object:

<snippet id='listview-grouping-groupdescriptors-businessobject' />

Create a `ViewModel` class as shown below:

<snippet id='listview-grouping-groupdescriptors-viewmodel' />


Add the `RadCollectionView` definition with two `PropertyGroupDescriptors` as shown in the next snippet:

<snippet id='listview-grouping-multilevel-definition' />

Include the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" 
```

The following image shows the final result.

![.NET MAUI ListView Multi-Level Grouping]()

> For a runnable demo with the CollectionView Multi-Level Grouping example, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **Calendar > Grouping** category.

## See Also

