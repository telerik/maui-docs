---
title: Improving TreeDataGrid Performance in .NET MAUI
description: Tips and tricks for optimizing the performance of the TreeDataGrid when dealing with large datasets and ideal layout practices.
type: how-to
page_title: Enhancing Performance for .NET MAUI TreeDataGrid with Large Datasets
meta_title: Enhancing Performance for .NET MAUI TreeDataGrid with Large Datasets
slug: improve-treedatagrid-performance-dotnet-maui
tags: treedatagrid, .net maui, performance, layouts, images, optimization, loadondemand, paging
res_type: kb
---

## Environment

| Product | Author | 
| --- | ---- | 
| Telerik UI for .NET MAUI TreeDataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I need tips and best practices to optimize performance when using the TreeDataGrid control with thousands of data entries. I want to know how layouts wrapping the control affect performance and whether images reduce performance.

This knowledge base article also answers the following questions:
- How to optimize performance for TreeDataGrid with large datasets?
- What are layout best practices for TreeDataGrid in .NET MAUI?
- Do images in TreeDataGrid affect performance?

## Solution

To optimize the performance of the TreeDataGrid in .NET MAUI, follow these steps:
* [Avoid Nesting in ScrollView or StackLayout](#avoid-nesting-in-scrollview-or-stacklayout)
* [Minimize Use of Templates in Columns](#minimize-use-of-templates-in-columns)
* [Implement Load-on-Demand or Paging](#implement-load-on-demand-or-paging)
* [Optimize Image Handling](#optimize-image-handling)

### Avoid Nesting in ScrollView or StackLayout

Position the TreeDataGrid inside a `Grid` with a `*` row height. Avoid nesting the control inside `Stack` or `ScrollView`. Nesting scrollable objects breaks UI virtualization and can impact performance. Refer to [Microsoft documentation](https://learn.microsoft.com/en-us/dotnet/maui/user-interface/controls/scrollview?view=net-maui-10.0) for details on scrollable objects.

Avoid wrapping Telerik MAUI TreeView, DataGrid, CollectionView, RichTextEditor, or PDF Viewer controls in a ScrollView. These controls have internal scrolling.

### Minimize Use of Templates in Columns 
 
Using [template columns](https://www.telerik.com/maui-ui/documentation/controls/datagrid/columns/column-types/template-column) or [cell content/edit templates](https://www.telerik.com/maui-ui/documentation/controls/treedatagrid/columns/cell-templates) can degrade performance. Rendering additional UI elements in templates forces the DataGrid to recreate and render elements inside these templates.

 Use built-in column types wherever possible. If custom rendering is required, use the [cell renderer approach](https://www.telerik.com/maui-ui/documentation/controls/treedatagrid/render-mode). This reduces the overhead caused by template re-rendering.

### Implement Load-on-Demand or Paging

Load large datasets incrementally using the [LoadOnDemand](https://www.telerik.com/maui-ui/documentation/controls/treedatagrid/load-on-demand) feature or divide them into manageable chunks with the [Paging](https://www.telerik.com/maui-ui/documentation/controls/treedatagrid/paging) feature.

### Optimize Image Handling

Columns with images can slow down scrolling due to repeated rendering of image elements. Implement caching strategies to optimize image loading. For more details, refer to this [image loading tutorial](https://www.youtube.com/watch?v=sDtx5ORYrmw&ab_channel=GeraldVersluis).

## See Also

- [TreeDataGrid Overview](https://www.telerik.com/maui-ui/documentation/controls/treedatagrid/overview)
- [TreeDataGrid Render Mode](https://www.telerik.com/maui-ui/documentation/controls/treedatagrid/render-mode)
- [TreeDataGrid Load On Demand](https://www.telerik.com/maui-ui/documentation/controls/treedatagrid/load-on-demand)
- [TreeDataGrid Paging](https://www.telerik.com/maui-ui/documentation/controls/treedatagrid/paging)
- [Image Loading Strategies](https://www.youtube.com/watch?v=sDtx5ORYrmw&ab_channel=GeraldVersluis)
