---
title: Ellipsis Mode
page_title: .NET MAUI DataPager Documentation - Ellipsis Mode
description: Learn what are the different options to display ellipsis in the .NET MAUI DataPager control.
position: 6
slug: datapager-ellipsis-mode
tags: ellipsis modes, data pager, maui, dotnet maui, paging
---

# .NET MAUI DataPager Ellipsis Mode

The ellipsis appears when the pages are more than the rendered numeric buttons. It provides a hint for the end user and indicates that there are undisplayed pages.

You can specify where the ellipsis is allowed to appear by setting the `EllipsisMode` (`enum` of type `Telerik.Maui.Controls.DataPager.DataPagerEllipsisMode`) property. The `EllipsisMode` controls whether the numeric buttons for the first/last page are replaced with an ellipsis (...) when there are more pages to the left/right.

The available options for `EllipsisMode` are:

* `None`&mdash;The ellipsis is disabled.
* `Before`&mdash;Display an ellipsis instead of the first numeric button.
* (Default) `After`&mdash; Display an ellipsis instead of the last numeric button.
* `Both`&mdash;Display an ellipsis on both sides.

The image below shows the ellipsis modes:

![.NET MAUI DataPager Ellipsis mode](images/datapager-ellispsismode.png)

## Example

Here is a quick example on how you can define the `EllipsisMode` in the DataPager.

**1.** Define the DataPager in XAML:

<snippet id='datapager-ellipsis-mode' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Define the `ViewModel`:

<snippet id='datapager-features-viewmodel' />

> For the DataPager Ellipsis Mode example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to the **DataPager > Features** category.

## Additional Resources

- [.NET MAUI DataPager Product Page](https://www.telerik.com/maui-ui/datagrid)
- [.NET MAUI DataPager Forum Page](https://www.telerik.com/forums/maui?tagId=1801)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [Paged Source]({%slug datapager-data-binding%})
- [Display Modes]({%slug datapager-display-mode%})
- [Page Configuration]({%slug datapager-page-configuration%})
- [Localization]({%slug datapager-localization%})
- [Commands in DataPager]({%slug datapager-commands%})
- [Styling]({%slug datapager-styling%})
- [Integration with DataGrid]({%slug datapager-datagrid%})