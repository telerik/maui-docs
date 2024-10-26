---
title: Displaying PDF Documents in a Popup in a .NET MAUI App
description: Learn how to load and display PDF documents within a popup in a .NET MAUI application.
type: how-to
page_title: How to Load and Display PDF Documents in a Popup in .NET MAUI
slug: load-display-pdf-documents-popup-net-maui
tags: pdfviewer, popup, .net maui, load, display, pdf, document
res_type: kb
---

## Environment


| Version | Product | Author | 
| --- | --- | ---- | 
| 7.1.0 | Telerik UI for .NET MAUI Popup and PDF Viewer | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

The need is to load and display a PDF document in a popup within a .NET MAUI application, with a preference for continuous scroll. This KB article demonstrates how to achieve this by using the [PDFViewer]({%slug pdfviewer-overview%}) and [RadPopup]({%slug popup-overview%}) components.

This KB article also answers the following questions:
- How can I display a PDF in a popup in .NET MAUI?
- Is it possible to load PDF documents in a popup with continuous scrolling?
- What steps are required to implement a PDF viewer in a popup for .NET MAUI applications?

## Solution

To display a PDF document in a popup, follow these steps:

**1.** Include the necessary namespace references to your .NET MAUI page.

```xml
<ContentPage xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             x:Class="YourNamespace.YourPage"
             xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui">
```

**2.** Add the `RadPopup` control to your page and set its `IsOpen` property to control the visibility. Inside the popup, place the `RadPdfViewer` to load and show the PDF document.

```xml
    <ContentPage.Content>
        <telerik:RadTemplatedButton Content="Show PDF"
                            Clicked="ShowPopupClicked">
        </telerik:RadTemplatedButton>
    </ContentPage.Content>

    <telerik:RadPopup.Popup>
        <telerik:RadPopup x:Name="popup"
                  OutsideBackgroundColor="#66000000"
                  Placement="Center"
                  VerticalOffset="8">
            <telerik:RadBorder BackgroundColor="#F9F9F9"
                       CornerRadius="8"
                       WidthRequest="600" HeightRequest="600">
                <Grid RowDefinitions="70,*">
                    <telerik:RadTemplatedButton Margin="20" Content="Close Popup" 
                                            Clicked="ClosePopup"/>
                    <telerik:RadPdfViewer x:Name="viewer"
                                      HeightRequest="500" 
                                      WidthRequest="500" 
                                      Grid.Row="1"/>
                </Grid>
            </telerik:RadBorder>
        </telerik:RadPopup>
    </telerik:RadPopup.Popup>
```

**3.** In the code-behind, handle the button click events to open and close the popup. Load the PDF document into the `RadPdfViewer` when the popup is shown.

```csharp
using System.Reflection;

namespace YourNamespace;

public partial class YourPage : ContentPage
{
    public YourPage()
    {
        InitializeComponent();
    }

    private void ShowPopupClicked(object sender, EventArgs e)
    {
        this.popup.IsOpen = true;
        Func<CancellationToken, Task<Stream>> streamFunc = ct => Task.Run(() =>
        {
            Assembly assembly = GetType().Assembly;
            string fileName = assembly.GetManifestResourceNames().FirstOrDefault(n => n.Contains("your-pdf-file.pdf"));
            Stream stream = assembly.GetManifestResourceStream(fileName);
            return stream;
        });
        this.viewer.Source = streamFunc;
    }

    private void ClosePopup(object sender, EventArgs e)
    {
        this.popup.IsOpen = false;
    }
}
```

For the example, ensure the PDF document (`your-pdf-file.pdf`) is added to your project with the `Build Action` set to `EmbeddedResource`.

## See Also

- [PDF Viewer Overview]({%slug pdfviewer-overview%})
- [Popup Overview]({%slug popup-overview%})
