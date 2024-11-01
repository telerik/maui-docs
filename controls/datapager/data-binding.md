---
title: Data Binding
page_title: .NET MAUI DataPager Documentation - Data Binding
description: Learn more about the ways for data binding in the Telerik UI for .NET MAUI DataPager control.
position: 1
slug: datapager-data-binding
---

# .NET MAUI DataPager Data Binding

The Telerik UI for .NET MAUI DataPager can page any collection that implements the `IEnumerable` interface. The only thing that the developer has to do is to pass the collection to the DataPager `Source` (`object`) property. 
After the collection is passed to the `Source` property, the collection splits into pages.

**Example with `Source` property**


## Binding to the PagedSource property of the RadDataPager

More often your collection will be a simple `List`, or an `ObservableCollection`,  or anything that is simply an `IEnumerable`. Unless you had paging in mind when you designed your project, it is almost certain that your data source will not be pageable out of the box. From here on you have to bind to the `PagedSource` (`IEnumerable`) property of the `RadDataPager`.

![DataPager PagedSource](images/)

The image above explains the steps how to bind to the `PagedSource` property of the DataPager:

1. Assign an `IEnumerable` to the `Source` of a `RadDataPager`, 
1. The `RadDataPager` wraps the `Source` in a `PageableCollection`. 
1. The `Source` is exposed through the `RadDataPager.PagedSource` property. 
1. Attach any number of ItemsControls to the `PagedSource` and they will be automatically paged. 


## See Also

- [.NET MAUI DataPager Product Page](https://www.telerik.com/maui-ui/datapager)
- [.NET MAUI DataPager Forum Page](https://www.telerik.com/forums/maui?tagId=1801)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
