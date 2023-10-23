---
title: Programmatically
page_title: .NET MAUI PDF Viewer Documentation - Programmatically
description: Learn how to search programmatically in the PDF Viewer without using the buil-in rtoolbar items. 
position: 3
slug: pdfviewer-search-programmatic
---

# .NET MAUI PDF Viewer Search Programmatically

The PDF Viewer for .NET MAUI allows you to programmatically search in the document.

## Manual Searching

You can use the `SearchAsync` method of the `SearchSettings` to manually initiate an async search operation with the provided text and search options.

Here is an example with the `SearchAsync` method and custom buttons for programmatically navigating to the next and previous search results:

**1.** Define the PDF Viewer control in XAML: 

<snippet id='pdfviewer-search-programmatic'/>

**2.** Add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** The `TextChanged` implementation where the `SearchAsync` method is used:

<snippet id='pdfviewer-entry-textchanged'/>

The following video shows the results from the completed example on Android:

![.NET MAUI PdfViewer Search Programmatically](../images/pdf-search-programmatically.gif "PDF Viewer Search Programmatically")

> For the runnable PDF Viewer Search Programmatic example, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **PdfViewer > Search category**.


## See Also

- [.NET MAUI PDF Viewer Forum Page](https://www.telerik.com/forums/maui?tagId=2059)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
