---
title: Migrating from Xamarin
page_title: .NET MAUI PdfViewer Documentation - Migrate from Xamarin
description: Learn how to migrate from Xamarin.Forms PdfViewer to .NET MAUI PdfViewer control.
position: 20
slug: pdfviewer-migrate-from-xamarin
---

# Migrate from Xamarin.Forms PdfViewer to .NET MAUI PdfViewer

Compared API changes in Xamarin.Forms PdfViewer and .NET MAUI PdfViewer are described in the tables below:

## Migrate the Namespaces

| Control | Control name | C# Namespace| XAML Namespcace |
| --------------- | --------------- | --------------- | --------------------------------------------------- |
| Xamarin PdfViewer | `RadPdfViewer` | xmlns:telerikPdfViewer="clr-namespace:Telerik.XamarinForms.PdfViewer;assembly=Telerik.XamarinForms.PdfViewer" | using Telerik.XamarinForms.PdfViewer; |
| .NET MAUI PdfViewer | `RadPdfViewer` |  xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |

## API Changes

| Xamarin PdfViewer | .NET MAUI PdfViewer |
| ------------- | --------------- |
| Text Selection | NA |
| Text Search | NA |
| `Localization` | NA |
| `ZoomInToolbarItem` | `PdfViewerZoomInToolbarItem` |
| `ZoomOutToolbarItem` | `PdfViewerZoomOutToolbarItem` |
| `NavigateToNextPageToolbarItem` | `PdfViewerNavigateToNextPageToolbarItem` |
| `NavigateToPreviousPageToolbarItem` | `PdfViewerNavigateToPreviousPageToolbarItem` |
| `NavigateToPageToolbarItem` | NA |
| `FitToWidthToolbarItem` | `PdfViewerFitToWidthToolbarItem` |
| `ToggleLayoutModeToolbarItem` | NA |
| `SearchToolbarItem` | NA |



## See Also

* [Migrating from Xamarin.Forms to .NET MAUI Application]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})
