---
title: Page Configuration
page_title: .NET MAUI DataPager Documentation - Page Page Configuration
description: Learn how to define the page buttons count, current page and the size of the page inside the Telerik .NET MAUI DataPager.
position: 14
slug: datapager-page-configuration
tags: page size, datapager, maui, dotnet maui
---

# .NET MAUI DataPager Page Configuration

This article explains the configuration oprions you can apply to the pages inside the DataPager control.

## Page Size

The DataPager splits the data into separate pages with a certain size. To specify the size of the page you have to use the `PageSize` (`int`) property. The default value is `10`.

By using the `PageSizes` (`IList<int>`) you can specify the pages that the end user can choose from.


## Current Page

The DataPager manages the current page depending on the user actions. In addition you can specify the current index of the DataPager by using the `PageIndex` (`int`) property.
The property contains the index of the currently selected page. The default value is `-1`.

Here is an example with the `PageIndex` set:

## Page Number Range

The DataPager allows you to define a range for the nummeric buttons that display the page numbers and choose a page within that range.

To implement page number range, use the following DataPager properties:

* `MinNumericButtonsCount` (`int`)&mdash;Specifies the minimum number of numeric buttons.
* `MaxNumericButtonsCount` (`int`)&mdash;Specifies the maximum number of numeric buttons.

## Item Spacing

You can specify the space between the items in the DataPager by setting the `ItemSpacing` (`double`) property. The default value is `0`.

## Example

Here is a sample example with `PageSize`, `PageIndex`, `PageSizes`, and `ItemSpacing` properties set.

**1.** Define the DataPager in XAML:

<snippet id='datapager-page-configuration' />

**2.** Add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Define the `ViewModel`:

<snippet id='datapager-features-viewmodel' />

> For the DataPager Page configuration example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to the **DataPager > Features** category.

## See Also

- [Paged Source]({%slug datapager-data-binding%})
- [Display Modes]({%slug datapager-display-mode%})
- [Ellipsis Modes]({%slug datapager-ellipsis-mode%})
- [Localization]({%slug datapager-localization%})
- [Commands in DataPager]({%slug datapager-commands%})
- [Styling]({%slug datapager-styling%})
- [Integration with DataGrid]({%slug datapager-datagrid%})