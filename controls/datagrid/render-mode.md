---
title: Render Mode
page_title: .NET MAUI DataGrid Documentation - Render Mode
description: Learn how to enable SkiaSharp rendering of the Telerik .NET MAUI DataGrid on all platforms.
position: 4
slug: datagrid-render-mode
---

# .NET MAUI DataGrid Render Mode

The .NET MAUI DataGrid is rendered differently depending on the target platform&mdash;on Android and Windows it uses the SkiaSharp library and on iOS and MacCatalyst by default it uses native elements.

With the `RenderMode` property you can enable SkiaSharp rendering on iOS and MacCatalyst:

* `RenderMode`(`DataGridRenderMode`)&mdash;Defines how the content of the DataGrid is rendered: using the defaults or via SkiaSharp. The available options are:
    * `Default`&mdash;Sets the rendering mode of the DataGrid content to the default. The default rendering mode is determined by the platform. On Android and WinUI, the DataGrid is rendered with SkiaSharp. On iOS and MacCatalyst, the DataGrid is rendered with the iOS <a href="https://developer.apple.com/documentation/uikit/uilabel" target="_blank"><code>UILabel</code></a> and <a href="https://developer.apple.com/documentation/uikit/uiview" target="_blank"><code>UIView</code></a> primitives.
    * `SkiaSharp`&mdash;SkiaSharp is used for rendering on all platforms.
 
Check below how you can enable the SkiaSharp render mode of the DataGrid:

<snippet id='datagrid-skia-rendering-xaml' />

>When using the `SkiaSharp` render mode, you can customize how each column is rendered through the `DataGridTextColumn`'s `CellRenderer` property. See [SkiaSharp Cell Renderer]({%slug datagrid-skiasharp-cell-renderer%}) for more details.

## See Also

- [SkiaSharp Cell Renderer]({%slug datagrid-skiasharp-cell-renderer%})
- [SkiaSharp GitHub](https://github.com/mono/SkiaSharp?#skiasharp)
- [SkiaSharp SKCanvas](https://learn.microsoft.com/en-us/dotnet/api/skiasharp.skcanvas)
