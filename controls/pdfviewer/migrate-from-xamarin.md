---
title: Migrating from Xamarin
page_title: .NET MAUI PDF Viewer Documentation - Migrate from Xamarin
description: Learn how to migrate from Xamarin.Forms PDF Viewer to .NET MAUI PDF Viewer control.
position: 20
slug: pdfviewer-migrate-from-xamarin
---

# Migrate from Xamarin.Forms PDF Viewer to .NET MAUI PDF Viewer

The tables below compare the API changes between the Xamarin.Forms PDF Viewer and .NET MAUI PDF Viewer.

## Namespace Changes

| Control | Control name | C# Namespace| XAML Namespcace |
| --------------- | --------------- | --------------- | --------------------------------------------------- |
| Xamarin PDF Viewer | `RadPdfViewer` | xmlns:telerikPdfViewer="clr-namespace:Telerik.XamarinForms.PdfViewer;assembly=Telerik.XamarinForms.PdfViewer" | using Telerik.XamarinForms.PdfViewer; |
| .NET MAUI PDF Viewer | `RadPdfViewer` |  xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |

## API Changes

| Xamarin PDF Viewer | .NET MAUI PDF Viewer |
| ------------- | --------------- |
| `ZoomInToolbarItem` | `PdfViewerZoomInToolbarItem` |
| `ZoomOutToolbarItem` | `PdfViewerZoomOutToolbarItem` |
| `NavigateToNextPageToolbarItem` | `PdfViewerNavigateToNextPageToolbarItem` |
| `NavigateToPreviousPageToolbarItem` | `PdfViewerNavigateToPreviousPageToolbarItem` |
| `NavigateToPageToolbarItem` | `PdfViewerNavigateToPageToolbarItem` |
| `FitToWidthToolbarItem` | `PdfViewerFitToWidthToolbarItem` |
| `ToggleLayoutModeToolbarItem` | `PdfViewerToggleLayoutModeToolbarItem` |
| `SearchToolbarItem` | `PdfViewerSearchToolbarItem`, `PdfViewerSearchNavigationToolbarItem` |
| N/A | `PdfViewerSelectionMenuButtonToolbarItem` |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI Application]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})
