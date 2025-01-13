---
title: Integration with DataGrid
page_title: .NET MAUI DataPager Documentation - Integration with DataGrid
description: Learn more about how to add paging functionality to the DataGrid for .NET MAUI.
position: 0
slug: datapager-datagrid
---

# .NET MAUI DataPager Integration with DataGrid

You can page the data of the [Telerik UI for .NET MAUI DataGrid]({%slug datagrid-overview%}) by using the DataPager control. However, the DataPager is independent of the DataGrid, and you can use it with any other `ItemsControl`.

![.NET MAUI DataPager with DataGrid](../images/datapager-datagrid-paging.png)

>Currently, the DataPager does not support the Telerik UI for .NET MAUI DataGrid [`LoadOnDemandCollaction`]({%slug datagrid-features-loadondemand%}#loadOnDemand-collection).

## Example

Here is an example of how to use the DataPager with the DataGrid control.

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

- [Paged Source]({%slug datapager-data-binding%})
- [Display Modes]({%slug datapager-display-mode%})
- [Ellipsis Modes]({%slug datapager-ellipsis-mode%})
- [Page Configuration]({%slug datapager-page-configuration%})
- [Localization]({%slug datapager-localization%})
- [Commands in DataPager]({%slug datapager-commands%})
- [Styling]({%slug datapager-styling%})
