---
title: Integration with CollectionView
page_title: .NET MAUI DataPager Documentation - Integration with CollectionView
description: Learn more about how to add paging functionality to the RadCollectionView for .NET MAUI.
position: 0
slug: datapager-collectionview
---

# .NET MAUI DataPager Integration with CollectionView

You can page the data of the [Telerik UI for .NET MAUI CollectionView]({%slug collectionview-overview%}) and [Microsoft .NET MAUI CollectionView](https://learn.microsoft.com/en-us/dotnet/maui/user-interface/controls/collectionview/?view=net-maui-9.0) by using the DataPager control.

![.NET MAUI DataPager with CollectionView](../images/datapager-collectionview-paging.png)

>Currently, the DataPager does not support the Telerik UI for .NET MAUI CollectionView [`LoadOnDemandCollection`]({%slug collectionview-load-on-demand-collection%}).

## Example

Here is an example of how to use the DataPager with the CollectionView control.

**1.** Define the DataPager and the CollectionView in XAML:

<snippet id='radcollectionview-datapager' />

**2.** Add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Define the `ViewModel`:

<snippet id='datapager-viewmodel' />

**4.** Define sample data:

<snippet id='datapager-data' />

> For the DataPager Integration example with Telerik and Microsoft MAUI CollectionView controls, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to the **DataPager > Integration** category.

## See Also

- [Paged Source]({%slug datapager-data-binding%})
- [Display Modes]({%slug datapager-display-mode%})
- [Ellipsis Modes]({%slug datapager-ellipsis-mode%})
- [Page Configuration]({%slug datapager-page-configuration%})
- [Localization]({%slug datapager-localization%})
- [Commands in DataPager]({%slug datapager-commands%})
- [Styling]({%slug datapager-styling%})
