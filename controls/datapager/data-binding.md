---
title: Source
page_title: .NET MAUI DataPager Documentation - Data Binding
description: Learn more about the ways for data binding in the Telerik UI for .NET MAUI DataPager control.
position: 3
slug: datapager-data-binding
---

# .NET MAUI DataPager Data Binding

The Telerik UI for .NET MAUI DataPager can page any collection that implements the `IEnumerable` interface. The only thing that the developer has to do is to pass the collection to the DataPager `Source` (`object`) property. 
After the collection is passed to the `Source` property, the collection splits into pages.

**Example with `Source` property**

**1.** Define the DataPager in XAML:

<snippet id='datapager-getting-started-xaml' />

**2.** Add a sample `ViewModel`:

<snippet id='datapager-features-viewmodel' />

**3.** Set the `ViewModel` as a `BindingContext`:

```C#
this.BindingContext = new ViewModel();
```

## Binding to the PagedSource property of the RadDataPager

More often your collection will be a simple `List`, or an `ObservableCollection`,  or a collection that inherits from `IEnumerable`. Unless you had paging in mind when you designed your project, it is almost certain that your data source will not be pageable out of the box. From here on you have to bind to the `PagedSource` (`IEnumerable`) property of the `RadDataPager`.

![DataPager PagedSource](images/)

The image above explains the steps how to bind to the `PagedSource` property of the DataPager:

1. Assign an `IEnumerable` to the `Source` of a `RadDataPager`, 
1. The `RadDataPager` wraps the `Source` in a `PageableCollection`. 
1. The `Source` is exposed through the `RadDataPager.PagedSource` property. 
1. Attach any number of ItemsControls to the `PagedSource` and they will be automatically paged.

Review the [Integration with DataGrid]({%slug datapager-datagrid%}) article, for more details how to use the `PagedSource` property.

## See Also

- [Display Modes]({%slug datapager-display-mode%})
- [Ellipsis Modes]({%slug datapager-ellipsis-mode%})
- [Page Configuration]({%slug datapager-page-configuration%})
- [Localization]({%slug datapager-localization%})
- [Commands in DataPager]({%slug datapager-commands%})
- [Styling]({%slug datapager-styling%})
- [Integration with DataGrid]({%slug datapager-datagrid%})
