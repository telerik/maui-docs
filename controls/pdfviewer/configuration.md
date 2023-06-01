---
title: Configuration
page_title: .NET MAUI PdfViewer Documentation - Configuration
description: Learn what are the options to configure the PdfViewer for .NET MAUI.
position: 3
slug: pdfviewer-configuration
---

# Configuration

The purpose of this help article is to show you the configuration options that PdfViewer for .NET MAUI provides.

## Setting the Zoom Level

PdfViewer exposes properties for applying min and max zoom values.

* `MaxZoomLevel`(`double`)&mdash;Defines the maximum magnification factor at which content could be maximized. The default value is 3.0
* `MinZoomLevel`(`double`)&mdash;Defines the minimum magnification factor at which content could be minimized. The default value is 0.3

>note In order to check how these properties works you should set the `ZoomIn` and `ZoomOut` commmands of the control. For more details please check the [Commands]({%slug pdfviewer-commands%}) article.

## Configure the spacing between the pages

* `PageSpacing`(`double`)&mdash;Defines the space between the pages of the Pdf Document. The default value is 20.0

## Configure the staring index of the page

* `VisiblePagesStartIndex`(`int`)&mdash;Defines the index at which the document will be displayed. The default value is 0.

## Customize the default BusyIndicator

When loading documents in the PdfViewer, a busy indicator visualizes. If the default look of the busy indicator does not suit your needs, you could easily define a custom template through the following property:

* `BusyIndicatorTemplate`(`DataTemplate`)&mdashSpecifies the template visualized while the Pdf Document is loading.

Here is an example how the custom BusyIndicatorTemplate could be defined:

<snippet id='pdfviewer-busy-indicator-template-xaml' />

Here is how the BusyIndicator Template looks:

![PdfViewer BusyIndicator Template](images/pdfviewer-busyindicator-template.png "PdfViewer BusyIndicator Template")

> For the PdfViewer BusyIndicator example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to PdfViewer -> Features category.

## See Also

- [Commands]({%slug pdfviewer-commands%})
- [PdfViewer Toolbar]({%slug pdfviewer-toolbar%})
