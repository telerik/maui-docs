---
title: Paging
page_title: .NET MAUI DataPager Documentation - Paging Support
description: Learn more about how to add paging functionality to the DataGrid for .NET MAUI.
position: 7
slug: datagrid-paging
---

# .NET MAUI DataPager Integration with DataGrid

You can page the data of the Telerik UI for .NET MAUI DataGrid by using the [DataPager]({%slug datapager-overview%}) control.

![.NET MAUI DataGrid Paging support](images/datagrid-datapager.png)

> Currently, the DataPager does not have a support for the DataGrid `LoadOnDemand` collection.

## DataPager Features

Here is a list of the most important features of the DataPager control:

* [Binding to `IEnumerable`]({%slug datapager-data-binding%})&mdash;Page any collection that implements the `IEnumerable` interface.
* Setting different [Ellipses modes]({%slug datapager-ellipsis-mode%})&mdash;The ellipsis appears when the count of the page numbers is greater than the count of the numeric buttons.
* Setting different [Display modes]({%slug datapager-display-mode%})&mdash;YOu can decide which of the visual elements in the DataPager will be visible.
* [Configure the pages]({%slug datapager-page-configuration%}) by setting
    * The current page&mdash;`PageIndex`;
    * The `PageSize` and `PageSizes`;
    * The spacing between the items in the pager&mdash;`ItemsSpacing` property;

* Customize the look of the:
    * [DataPager]({%slug datapager-styling%})
    * [NavigationView]({%slug datapager-styling-navigationview%})
    * [Navigation and Numeric Buttons]({%slug datapager-styling-buttons%})
    * [PageSizes]({%slug datapager-styling-pagesize%})

## Example 

Here is an example how to use DataPager with DataGrid control.

**1.** Define the DataPager and the DataPager in XAML:

<snippet id='datagrid-datapager' />

**2.** Add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Define the `ViewModel`:

<snippet id='datagrid-datapager-viewmodel' />

**4.** Define sample data:

<snippet id='datagrid-datapager-data' />

> For the DataPager Integration with DataGrid example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to the **DataPager > Integration** category.

## See Also

- [Aggregating Data in the Telerik UI for .NET MAUI DataGrid]({%slug datagrid-aggregates%})
- [Sorting .NET MAUI DataGrid Records]({%slug datagrid-sorting-overview%})
- [Styling the Appearance of the DataGrid]({%slug datagrid-styling%})