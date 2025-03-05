---
title: Viewport Settings
page_title: .NET MAUI PDF Viewer Documentation - Viewport Settings
description: Learn how to get and change the viewport of the Telerik UI for .NET MAUI PDF Viewer control.
position: 5
slug: pdfviewer-viewport
---

# Viewport Settings

The Telerik UI for .NET MAUI PDF Viewer provides an API for getting and manipulating its viewport through the `Viewport` property and `ChangeViewport()` method. 

The viewport is the window where the <a href="https://www.telerik.com/maui-ui/pdf-viewer" target="_blank">.NET MAUI PDF Viewer</a> displays its content and users can change the viewport through zooming, panning, and scrolling:

![.NET MAUI PDF Viewer Viewport](images/pdfviewer-viewport.gif)

To explain how the viewport works, we first need to clarify the content of the PDF Viewer and how to define its size. The content of the PDF Viewer refers to the PDF document itself (the document pages). The PDF Viewer offers two layout modes: `SinglePage` and `ContinuousScroll`, each utilizing different approaches to arrange the document pages. The method of defining the content varies based on the selected layout mode.

>tip For detailed information on the available layout modes, check the [Viewing Modes]({%slug pdfviewer-layout-modes%}) topic.

## Layout Modes

The PDF Viewer supports two layout modes that you can set through its `LayoutMode` property:

* [`SinglePage`](#singlepage-layout-mode)
* [`ContinuousScroll`](#continuousscroll-layout-mode)

### SinglePage Layout Mode

With the `SinglePage` layout mode, the PDF Viewer shows one page at a time (the pages are stacked), so the content is the current page and the content size is the size of that page. If the document contains pages with different sizes, the content size is changed.

The viewport position is calculated relative to the current page.

![.NET MAUI PDF Viewer Single Page Layout Mode](images/pdfviewer-viewport-singlepage.png)

### ContinuousScroll Layout Mode

In the `ContinuousScroll` layout mode, content is defined as all the document pages. In this mode, the pages are vertically ordered one below another with spacing between them, and they are horizontally centered. If the document contains pages with different widths, some pages may not be aligned at the `0` horizontal position.

The content width is determined by the widest page in the document. The content height is calculated by summing the heights of all the pages along with the distances between them. The spacing between pages is controlled by the `PageSpacing` property of the PDF Viewer.

So, the viewport position is calculated relative to the whole content (all pages and distances):

![.NET MAUI PdfViewer Continuous Scroll Layout Mode](images/pdfviewer-viewport-continuous.png)

No matter which layout mode is selected, the viewport is the "window" which moves over the defined content and renders the PDF elements currently positioned in it.

The `Viewport` property of the PDF Viewer is of type `Microsoft.Maui.Graphics.Rect` and can be defined by its top left corner at the (x, y) position and width and height values. Keep in mind it's possible to have negative X and Y values in case the viewport becomes bigger than the content itself.

## Example: Navigating to a Page 

The example below demonstrates how to use the `ChangeViewport` method and navigate to the last page of the document in the `ContinuousScroll` and `SinglePage` layout modes as well as how to access the current viewport.

**1.** Define the `RadPdfViewer` and `RadPdfToolbar`:

```XAML
<Grid>
    <Grid.RowDefinitions>
        <RowDefinition Height="Auto"/>
        <RowDefinition Height="Auto"/>
        <RowDefinition Height="Auto"/>
        <RowDefinition Height="*"/>
    </Grid.RowDefinitions>
    <HorizontalStackLayout>
        <Button Text="Get Viewport" Clicked="GetViewport_Clicked" />
        <Label x:Name="viewportLabel" VerticalOptions="Center"/>
    </HorizontalStackLayout>
    <HorizontalStackLayout Grid.Row="1">
        <Button Text="Change Viewport" Clicked="ChangeViewport_Clicked" />
    </HorizontalStackLayout>
    <telerik:RadPdfViewerToolbar PdfViewer="{x:Reference pdfViewer1 }" x:Name="toolbar1" Grid.Row="2">
        <telerik:PdfViewerZoomInToolbarItem />
        <telerik:PdfViewerZoomOutToolbarItem />
        <telerik:PdfViewerNavigateToPreviousPageToolbarItem />
        <telerik:PdfViewerNavigateToNextPageToolbarItem />
        <telerik:PdfViewerToggleLayoutModeToolbarItem />
    </telerik:RadPdfViewerToolbar>
    <telerik:RadPdfViewer x:Name="pdfViewer" Grid.Row="3" />
</Grid>
```

**2.** Add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Load the document in the PDF Viewer:

```C#
Func<CancellationToken, Task<Stream>> streamFunc = ct => Task.Run(() =>
{
    Assembly assembly = typeof(MainPage).Assembly;
    string fileName = assembly.GetManifestResourceNames().FirstOrDefault(n => n.Contains("pdf-overview.pdf"));
    Stream stream = assembly.GetManifestResourceStream(fileName);
    return stream;
});
this.pdfViewer1.Source = streamFunc;
```

**3.** Get the current viewport position and size:

```C#
private void GetViewport_Clicked(object sender, EventArgs e)
{
    this.viewportLabel.Text = this.pdfViewer.Viewport.ToString();
}
```

**4.** Manipulate the viewport of the PDF Viewer:

```C#
private void ChangeViewport_Clicked(object sender, EventArgs e)
{
    RadFixedDocument document = this.pdfViewer1.Document;
    var currentViewport = this.pdfViewer1.Viewport;

    if (this.pdfViewer1.LayoutMode == LayoutMode.ContinuousScroll)
    {
        double pagesHeight = 0;

        for (int i = 0; i < document.Pages.Count - 1; i++)
        {
            pagesHeight += document.Pages[i].Size.Height;
            pagesHeight += this.pdfViewer1.PageSpacing;
        }
        this.pdfViewer1.ChangeViewport(new Rect(0, pagesHeight, currentViewport.Width, currentViewport.Height));
    }
    else
    {
        this.pdfViewer1.NavigateToPage(document.Pages.Count - 1);
        this.pdfViewer1.ChangeViewport(new Rect(0, 0, currentViewport.Width, currentViewport.Height));
    }
}
```

## See Also

- [Commands]({%slug pdfviewer-commands%})
