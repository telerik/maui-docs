---
title: Custom Search
page_title: .NET MAUI PDF Viewer Documentation - Custom Search
description: Learn how to implement custom search in the .NET MAUI PDF Viewer control. 
position: 0
slug: pdfviewer-search-custom
---

# .NET MAUI PDF Viewer Search Programmatically

You can extend the search functionality by implementing a custom `TextSearchWorker`. The `TextSearchWorker` object performs the actual search according to the search criteria.

The example below implements a custom search by multiple words - any word that is entered into the input is considered as a separate search text.

**1.** Create a custom class that derives from `TextSearchWorker` - you'd need to override the Search method that returns `TextSearchResult` object:



**2.** Apply the `MultipleWordsSearchWorker` object to the `TextSearchWorker` property of the `SearchSettings` of `RadPdfViewer`:


## See Also

- [.NET MAUI PDF Viewer Product Page](https://www.telerik.com/maui-ui/pdfviewer)
- [.NET MAUI PDF Viewer Forum Page](https://www.telerik.com/forums/maui?tagId=2059)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
