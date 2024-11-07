---
title: Binding a Source
page_title: .NET MAUI DataPager Documentation - Data Binding
description: Learn more about the ways you can bind data to the Telerik UI for .NET MAUI DataPager control.
position: 3
slug: datapager-data-binding
---

# .NET MAUI DataPager Data Source Binding

The Telerik UI for .NET MAUI DataPager can page any collection that implements the `IEnumerable` interface. 

To bind the desired collection to the DataPager, pass the collection to the DataPager's `Source` (`object`) property.  This will split the data into pages.

The following demonstrates how to use the `Source` property to bind a collection:

**1.** Define the DataPager in XAML:

<snippet id='datapager-getting-started-xaml' />

**2.** Add a sample `ViewModel`:

<snippet id='datapager-features-viewmodel' />

**3.** Set the `ViewModel` as a `BindingContext`:

```C#
this.BindingContext = new ViewModel();
```

## Binding to the PagedSource Property of the RadDataPager

Often, your collection will be a simple `List`, an `ObservableCollection`, or a collection that inherits from `IEnumerable`. Unless you had paging in mind when you designed your project, it is almost certain that your data source will not be pageable out of the box. In these scenarios, bind to the `PagedSource` (`IEnumerable`) property of the `RadDataPager`.

![DataPager PagedSource](images/)

The image above illustrates the process for binding to the `PagedSource` property of the DataPager:

1. You assign an `IEnumerable` to the `Source` of a `RadDataPager`.
1. The `RadDataPager` wraps the `Source` in a `PageableCollection`.
1. The `Source` is exposed through the `RadDataPager.PagedSource` property.
1. You attach any number of item controls to the `PagedSource` and they are paged automatically.

Review the [Integration with DataGrid]({%slug datapager-datagrid%}) article, for more details how to use the `PagedSource` property.

## See Also

- [Display Modes]({%slug datapager-display-mode%})
- [Ellipsis Modes]({%slug datapager-ellipsis-mode%})
- [Page Configuration]({%slug datapager-page-configuration%})
- [Localization]({%slug datapager-localization%})
- [Commands in DataPager]({%slug datapager-commands%})
- [Styling]({%slug datapager-styling%})
- [Integration with DataGrid]({%slug datapager-datagrid%})
