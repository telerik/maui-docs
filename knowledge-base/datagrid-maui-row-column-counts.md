---
title: Retrieving Row and Column Counts in DataGrid for MAUI
description: Learn how to obtain the number of rows and columns in a DataGrid for MAUI.
type: how-to
page_title: How to Get Row and Column Counts in MAUI DataGrid
slug: datagrid-maui-row-column-counts
tags: datagrid, maui, rows, columns, count
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 10.0.0 | DataGrid for .NET MAUI | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I need to determine the number of rows and columns in a DataGrid.

 This knowledge base article also answers the following questions:
- How can I find out how many rows are in my DataGrid?
- What is the method to know the number of columns in DataGrid?
- Can I programmatically retrieve row and column counts in DataGrid?

## Solution

To retrieve the number of rows and columns in a DataGrid for MAUI, follow the steps below:

**1.** Obtain the number of rows. The DataGrid generates rows based on the count of items in the collection bound to the `ItemsSource` property. Use the following code to get the number of rows:

```csharp
var rowNumber = (this.dataGrid.ItemsSource as ObservableCollection<FilesData>).Count.ToString();
```

**2.** Obtain the number of columns. The DataGrid exposes a `Columns` collection. Access this collection to get the amount of columns:

```csharp
var columnNumber = this.dataGrid.Columns.Count.ToString();
```

These snippets give the total number of rows and columns in the DataGrid.

## See Also

- [DataGrid for MAUI Overview]({%slug datagrid-overview%})

