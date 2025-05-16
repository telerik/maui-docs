---
title: Integration with TreeDataGrid
page_title: .NET MAUI DataPager Documentation - Integration with TreeDataGrid
description: Learn more about how to add paging functionality to the TreeDataGrid for .NET MAUI.
position: 0
slug: datapager-treedatagrid
---

# .NET MAUI DataPager Integration with TreeDataGrid

You can page the data of the [Telerik UI for .NET MAUI TreeDataGrid]({%slug treedatagrid-overview%}) by using the DataPager control.

![.NET MAUI DataPager with TreeDataGrid](../images/datapager-treedatagrid-paging.png)

>Currently, the DataPager does not support the Telerik UI for .NET MAUI TreeDataGrid [`LoadOnDemandCollection`]({%slug treedatagrid-features-loadondemand%}#loadOnDemand-collection).

## Example

Here is an example of how to use the DataPager with the TreeDataGrid control.

**1.** Define the DataPager and the TreeDataGrid in XAML:

<snippet id='treedatagrid-datapager' />

**2.** Add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Create a sample `Data` class:

<snippet id='treedatagrid-data-model' />

**4.** Add the `ViewModel` class:

<snippet id='treedatagrid-viewmodel' />

> For the DataPager Integration with TreeDataGrid example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to the **DataPager > Integration** category.

## See Also

- [Paged Source]({%slug datapager-data-binding%})
- [Display Modes]({%slug datapager-display-mode%})
- [Ellipsis Modes]({%slug datapager-ellipsis-mode%})
- [Page Configuration]({%slug datapager-page-configuration%})
- [Localization]({%slug datapager-localization%})
- [Commands in DataPager]({%slug datapager-commands%})
- [Styling]({%slug datapager-styling%})
