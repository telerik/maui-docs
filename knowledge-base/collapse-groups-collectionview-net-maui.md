---
title: Collapsing All Groups Initially in CollectionView for .NET MAUI
description: Learn how to start with all groups collapsed within the CollectionView control in .NET MAUI applications.
type: how-to
page_title: How to Collapse Groups on Initial Load in .NET MAUI CollectionView
slug: collapse-groups-collectionview-net-maui
tags: collectionview, .net maui, groupdescriptor, collapse, initial load
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 10.1.0 | Telerik UI for .NET MAUI CollectionView | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

In a .NET MAUI application using the CollectionView component, I want all groups to be collapsed initially when the data is loaded. How can I achieve this behavior?

This knowledge base article also answers the following questions:
- How to start with all groups collapsed in CollectionView for .NET MAUI?
- What method collapses all groups in a CollectionView upon data load?
- Where to call the CollapseAll method in CollectionView for .NET MAUI?

## Solution

To ensure that all groups are collapsed initially when the CollectionView control loads, utilize the `CollapseAll` method. Call this method once the data is fully loaded into the control. One effective approach is to use the `CollectionView.Loaded` event. However, introduce a short delay before calling `CollapseAll` to guarantee that data loading is complete. 

Here's how you can implement this solution:

1. Subscribe to the `Loaded` event of the `RadCollectionView`. You can do this in your XAML file:

```xml
<telerik:RadCollectionView x:Name="myCollectionView" Loaded="myCollectionView_Loaded">
```

2. Implement the event handler in your code-behind file. In this handler, introduce a delay and then call the `CollapseAll` method:

```csharp
private async void myCollectionView_Loaded(object sender, EventArgs e)
{
    var data = this.myCollectionView.GetDataView();
    await Task.Delay(500); // Adjust the delay as necessary.
    data.CollapseAll();
}
```

Note: The delay (`Task.Delay(500)`) might need adjustment based on the specific data loading time in your application. The key is to ensure that the data is fully loaded before calling the `CollapseAll` method.

## See Also

- [CollectionView Overview]({%slug collectionview-overview%})
- [Grouping in CollectionView]({%slug collectionview-grouping%})
