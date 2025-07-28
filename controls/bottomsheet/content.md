---
title: Content
page_title: .NET MAUI BottomSheet Documentation - Content
description: Learn more about how to set a content inside the Telerik UI for .NET MAUI BottomSheet control.
position: 3
slug: bottomsheet-content
---

# .NET MAUI BottomSheet Content

The purpose of this help article is to show you how to define content in the Telerik .NET MAUI BottomSheet control.

The BottomSheet control contains a main content and a bottom sheet content.

* The main content is the part that is always visible in the control.

* Set a content to the bottom sheet using the `BottomSheetContent` (`View`) property.

Here is a sample scenario when using the Telerik .NET MAUI [`RadCollectionView`]({%slug collectionview-overview%}) in the main content of the BottomSheet and a detailed view in the `BottomSheetContent`.

**1.** Define the sample data model:

<snippet id='bottomsheet-data-model' />

**2.** Define the `ViewModel`:

<snippet id='bottomsheet-view-model' />

**3.** Define the BottomSheet in XAML with `RadCollectionView`:

<snippet id='bottomsheet-animation-swipe' />

**4.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**5.** Add the following code for the `RadCollectionView.ItemTapped` event handler:

<snippet id='bottomsheet-content-tapped-event' />

> For a runnable example with the BottomSheet Content scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and review all **BottomSheet** example.

## See Also

- [Animation when opening and closing the bottom sheet]({%slug bottomsheet-animation%})
- [Style the BottomSheet]({%slug bottomsheet-styling%})
- [Events]({%slug bottomsheet-events%})
- [Methods]({%slug bottomsheet-methods%})