---
title: Display Mode
page_title: .NET MAUI DataPager Documentation - Display Mode
description: Learn what are the different options to display buttons in the .NET MAUI DataPager control.
position: 14
slug: datapager-display-mode
tags: display mode
---

# .NET MAUI DataPager Display Mode

The DataPager allows you to decide which of its visual elements to be visibleby setting the `DisplayMode` (`enum` of type `Telerik.Maui.Controls.DataPager.DataPagerDisplayMode`) property.

The available options for `DisplayMode` are:

* `None`&mdash;
* `FirstPageButton`&mdash;
* `PrevPageButton`&mdash;
* `NumericButtons`&mdash;
* `NavigationComboBox`&mdash;
* `NextPageButton`&mdash;
* `LastPageButton`&mdash;
* `PageSizesView`&mdash;
* `NavigationView`&mdash;

**Example with `DisplayMode`**

Here is a quick example on how you can define the `DisplayMode` to the DataPager.

**1.** Define the DataPager in XAML:

<snippet id='datapager-display-mode' />

**2.** Add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Define the `ViewModel`:

<snippet id='datapager-features-viewmodel' />

> For the DataPager Display Mode example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to the **DataPager > Features** category.

## Adaptive Display Modes

DataPager gives you the option to customize the default way how the elements in the pager are arranged by using the `AdaptiveDisplayModes` property.

* `AdaptiveDisplayModes` (`IList<DataPagerDisplayMode>`)&mdash;Specifies a list of desired combinations of elements that should be displayed. The actual elements that are displayed are the result of this property.

**Example with `AdaptiveDisplayModes`**

Here is a quick example on how you can define the `DisplayMode` to the DataPager.

**1.** Define the DataPager in XAML:

<snippet id='datapager-adaptivedisplay-mode' />

**2.** Add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Define the `ViewModel`:

<snippet id='datapager-features-viewmodel' />

> For the DataPager Display Mode example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to the **DataPager > Features** category.

## Additional Resources

- [.NET MAUI DataPager Product Page](https://www.telerik.com/maui-ui/datagrid)
- [.NET MAUI DataPager Forum Page](https://www.telerik.com/forums/maui?tagId=1801)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Paged Source]({%slug datapager-data-binding%})
- [Ellipsis Modes]({%slug datapager-ellipsis-mode%})
- [Page Configuration]({%slug datapager-page-configuration%})
- [Localization]({%slug datapager-localization%})
- [Commands in DataPager]({%slug datapager-commands%})
- [Styling]({%slug datapager-styling%})
- [Integration with DataGrid]({%slug datapager-datagrid%})