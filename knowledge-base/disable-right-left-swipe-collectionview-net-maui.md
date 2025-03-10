---
title: Disabling Right or Left Swipe in CollectionView for .NET MAUI
description: Learn how to disable right or left swipe action in CollectionView for .NET MAUI while keeping left swipe enabled.
type: how-to
page_title: How to Disable Right or Left Swipe in .NET MAUI CollectionView
slug: disable-right-left-swipe-collectionview-net-maui
tags: collectionview, .net maui, swipe, disable right swipe
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 10.0.0 | CollectionView for .NET MAUI | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

You're using the CollectionView in a .NET MAUI application and have enabled item swiping with `IsItemSwipeEnabled` set to `true`. However, you want to disable the right or left swipe action while keeping the left or right swipe action enabled. 

This knowledge base article also answers the following questions:

- How to disable right swipe in CollectionView?
- How to disable left swipe in CollectionView?
- Can I enable only left swipe in CollectionView for .NET MAUI?
- Can I enable only right swipe in CollectionView for .NET MAUI?
- How to handle swipe actions differently in CollectionView?



## Solution

To disable the right swipe (left -to-right swipe direction) in a `RadCollectionView` while allowing the left swipe (right-to-left direction), subscribe to the `Swiping` event. In the event handler, determine the swipe direction by examining the `Offset` property. If the `Offset` is less than 0, indicating a right-to-left swipe direction, then call the `EndItemSwipe()` method to cancel the swipe action.

If you want to disable the left swipe (right-to-left swipe direction) the Offset must be greater than 0.

**1.** Define the `RadCollectionView` in XAML:

```xml
<telerik:RadCollectionView x:Name="collectionView"
                           IsItemSwipeEnabled="True"
                           Swiping="collectionView_Swiping">
```

**2.** Implement the event handler in your code-behind to disable the right swipe:

```csharp
private void collectionView_Swiping(object sender, Telerik.Maui.Controls.CollectionView.CollectionViewSwipingEventArgs e)
{
	// Disable right swipe (left-to-right direction)
	//if (e.Offset > 0)
	//{
	//	this.collectionView.EndItemSwipe(false);
	//}

	// Disable left swipe (right-to-left direction)
	if (e.Offset < 0)
	{
		this.collectionView.EndItemSwipe(false);
	}
}
```

By using this approach, the collection view will only respond to right swipes, effectively disabling the left swipe functionality.

## See Also

- [CollectionView Overview](https://docs.telerik.com/devtools/maui/controls/collectionview/overview)
- [Handling Swipes in CollectionView](https://docs.telerik.com/devtools/maui/controls/collectionview/item-swipe/overview)
