---
title: Configuration
page_title: .NET MAUI PDF Viewer Documentation - Configuration
description: Learn how to configure the selection options, and selection menu in the PDF Viewer for .NET MAUI.
position: 2
slug: pdfviewer-selection-configuration
---

# .NET MAUI PDF Viewer Selection Configuration

The Telerik UI for .NET MAUI PDF Viewer exposes `SelectionSettings ` property which you can use to configure the colors applied to the selected text and completely customize the displayed selection menu.

This article lists the `SelectionSettings` properties that allow you to customize the selection.

By default the selection is enabled. If you want to disable the selection, set the `IsSelectionEnabled` to `False`.

## Selection Fill and Indicator Color

* `SelectionFill`&mdash;Specifies the background color applied to the selected text.
* `SelectionIndicatorColor`&mdash;Specifies the color of both handles around the selected text used to modify the selection. This is applicable on mobile.

## Context Menu

When seleting a text, a default context menu opens with a `Copy` action. If you want to customize the selection (context) menu use the follwing properties:

* `MenuItems` (`PdfViewerSelectionMenuItemCollection`)&mdash;Specifies a collection of menu items that are displayed in the SelectionMenu.

## Customize the Selection Menu

* `SelectionMenuControlTemplate` (`ControlTemplate`)&mdash;Specifies the `ControlTemplate` of the selection (context) menu that is used to display the items.

The defualt control templates for desktop and mobile:

<snippet id='pdfviewer-selectionmenu-controltemplate' />

## Selection Menu Item

Add items inside the `MenuItems` collection by using the `PdfViewerSelectionMenuItem`. The `PdfViewerSelectionMenuItem` has the following properties:

* `Text` (`string`)&mdash;Specifies the text of the `PdfViewerSelectionMenuItem`.
* `Command` (`ICommand`)&mdash;Specifies the command associated with the `PdfViewerSelectionMenuItem`.

## Example: PDF viewer Custom Selection Menu

**1.** Add the PDF Viewer definition with the event:

<snippet id='pdfviewer-text-selection-xaml' />

**2.** Define an implicit style for the `PdfViewerSelectionMenu`:

<snippet id='pdfviewer-selectionmenu-style' />

**3.** Add the following view model for the `Command`:

<snippet id='pdfviewer-textselection-viewmodel' />

**4.** Set PDF document to the PDF viewer `Source`:

<snippet id='pdfviewer-getting-started' />

This is how the selection looks after applying a customization:

![.NET MAUI PDF Viewer Selection Customization](../images/pdf-selection-customization.gif)

> For the runnable PDF Viewer Selection example, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **PdfViewer > Selection category**.

## See Also

- [.NET MAUI PDF Viewer Forum Page](https://www.telerik.com/forums/maui?tagId=2059)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
