---
title: Custom Search
page_title: .NET MAUI PDF Viewer Documentation - Custom Search
description: Learn how to implement custom search in the .NET MAUI PDF Viewer control. 
position: 4
slug: pdfviewer-search-custom
---

# .NET MAUI PDF Viewer Custom Search

You can extend the search functionality by implementing a custom `TextSearchWorker`. The `TextSearchWorker` object performs the actual search according to the search criteria.

The example below implements a custom search by multiple words-any word that is entered into the input is considered as a separate search text.

**1.** Create a custom class that derives from `Telerik.Maui.Controls.PdfViewer.PdfViewerTextSearchWorker`-you need to override the `Search` method that returns `TextSearchResult` object:

```C#
public class MultipleWordsSearchWorker : Telerik.Maui.Controls.PdfViewer.PdfViewerTextSearchWorker
{
    protected override PdfViewerTextSearchResult Search(PdfViewerSearchContext context)
    {
        string regex = GetMultiWordRegex(context.Text);
        TextSearchOptions regexOptions = new TextSearchOptions { UseRegularExpression = true };
        PdfViewerSearchContext newContext = new PdfViewerSearchContext(context.PdfViewer, context.Document, regex, regexOptions, context.SearchProgress, context.CancellationToken);

        return base.Search(newContext);
    }
   
    private static string GetMultiWordRegex(string text)
    {
        string[] words = text.Split(new string[] { " " }, StringSplitOptions.RemoveEmptyEntries);
        StringBuilder sb = new StringBuilder();

        for (int i = 0; i < words.Length; i++)
        {
            if (i > 0)
            {
                sb.Append("|");
            }

            string expr = string.Format(@"({0})", words[i]);
            sb.Append(expr);
        }

        return sb.ToString();
    }
}
```

**2.** Apply the `MultipleWordsSearchWorker` object to the `TextSearchWorker` property of the `SearchSettings` of `RadPdfViewer`:

```XAML
<telerik:RadPdfViewer x:Name="pdfViewer">
    <telerik:RadPdfViewer.SearchSettings>
        <telerik:PdfViewerSearchSettings MainSearchResultFill="#99FF7F7F"
                                            SearchResultsStringFormat="Result: {0}, Total: {2}"
                                            SearchResultsFill="#997FC9FF"
                                            TextSearchTrigger="TextChanged">
            <telerik:PdfViewerSearchSettings.TextSearchWorker>
                <local:MultipleWordsSearchWorker/>
            </telerik:PdfViewerSearchSettings.TextSearchWorker>
        </telerik:PdfViewerSearchSettings>
    </telerik:RadPdfViewer.SearchSettings>
</telerik:RadPdfViewer >
```

**3.** Set the `Source` to the PDF viewer:

<snippet id='pdfviewer-search-settings-loading-document' />

**4.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

## See Also

- [.NET MAUI PDF Viewer Forum Page](https://www.telerik.com/forums/maui?tagId=2059)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
