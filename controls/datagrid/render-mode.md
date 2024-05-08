---
title: Render Mode
page_title: .NET MAUI DataGrid Documentation - Render Mode
description: Learn how to enable SkiaSharp rendering of the Telerik .NET MAUI DataGrid on all platforms.
position: 4
slug: datagrid-render-mode
---

# .NET MAUI DataGrid Render Mode

The .NET MAUI DataGrid is rendered differently depending on the target platform - on Android and Windows it uses the SkiaSharp library and on iOS and MacCatalyst by default it uses native elements.

With the `RenderMode` property you can enable SkiaSharp rendering on iOS and MacCatalyst:

* `RenderMode`(`DataGridRenderMode`)&mdash;Defines how the content of the DataGrid is rendered - via SkiaSharp or other means. The available options are:
    * `Default`&mdash;Defines the default render mode of the content of the DataGrid which is different in the different platforms. In Android and WinUI the DataGrid is rendered with SkiaSharp. In iOS and MacCatalyst it is rendered with the iOS UILabel and UIView primitives.
    * `SkiaSharp`&mdash;SkiaSharp is used for rendering on all platforms.
 
Check below how you can enable the SkiaSharp render mode of the DataGrid:

<snippet id='datagrid-skia-rendering-xaml' />

>When using `SkiaSharp` render mmode, you can completely customize how each column is rendered through the `DataGridTextColumn`'`CellRenderer` property. See [SkiaSharp Cell Renderer]({%slug datagrid-skiasharp-cell-renderer%}) topic for more details.

## See Also
- [SkiaSharp Cell Renderer]({%slug datagrid-skiasharp-cell-renderer%})