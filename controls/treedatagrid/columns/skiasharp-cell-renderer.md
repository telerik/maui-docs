---
title: SkiaSharp Cell Renderer
page_title: .NET MAUI TreeDataGrid Documentation - SkiaSharp Cell Renderer
description: Learn how to define a custom SkiaSharp cell renderer for the TreeDataGrid columns.
position: 4
slug: treedatagrid-skiasharp-cell-renderer
---

# .NET MAUI TreeDataGrid SkiaSharp Cell Renderer

When your [.NET MAUI TreeDataGrid]({%slug treedatagrid-overview%}) is rendered with the SkiaSharp library, you can extend the functionality of a DataGrid column and render custom cell content. 

* `CellRenderer`(`DataGridCellRenderer`)&mdash;Defines a renderer that allows custom rendering of cells when the TreeDataGrid is rendered with SkiaSharp. To use this in iOS and MacCatalyst, the `RadTreeDataGrid`.`RenderMode` needs to be set to `SkiaSharp`.

>Check the [Render Mode]({%slug treedatagrid-render-mode%}) topic for more information on the TreeDataGrid SkiaSharp rendering.

The `DataGridCellRenderer` provides the following methods you can override to define any custom SkiaSharp content inside each cell:

* `MeasureContainer`&mdash;Returns the desired size for the current item in device independent pixels.
* `RenderContainer`&mdash;Renders any custom content for the current item. Invoke the base implementation of this method if you want to render the default render content.
* `RequestRender`&mdash;Makes a request for a render pass to be scheduled.
* `OnRenderStarted`&mdash;Marks the beginning of the rendering of the cells related to this renderer.
* `OnRenderCompleted`&mdash;Marks the end of the rendering of the cells related to this renderer.

## See Also

- [Render Mode]({%slug datagrid-render-mode%})
- [SkiaSharp GitHub](https://github.com/mono/SkiaSharp?#skiasharp)
- [SkiaSharp SKCanvas](https://learn.microsoft.com/en-us/dotnet/api/skiasharp.skcanvas)
