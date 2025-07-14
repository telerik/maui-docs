---
title: Programmatically Scrolling a Column into View in DataGrid for MAUI
description: Learn how to programmatically scroll a column into view in DataGrid for MAUI using reflection to access an internal API.
type: how-to
page_title: Programmatic Column Scrolling in MAUI DataGrid
meta_title: Programmatic Column Scrolling in MAUI DataGrid
slug: maui-datagrid-scroll-column-into-view
tags: maui, datagrid, scroll-column
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.0.1 | Telerik UI for .NET MAUI DataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to programmatically scroll a column into view in the DataGrid for MAUI. The `ScrollItemIntoView` method appears to scroll rows into view but does not provide functionality for columns. 

This knowledge base article also answers the following questions:
- How can I scroll to a specific column programmatically in MAUI DataGrid?
- Is there a way to scroll columns into view using reflection?
- How do I use the `ScrollColumnIntoView` method in MAUI DataGrid?

## Solution

Use the internal `ScrollColumnIntoView` method via reflection. Below is an example implementation triggered by a button click.

1. Access the column you want to scroll into view from the `Columns` collection.
2. Use reflection to access the internal `ScrollColumnIntoView` method.
3. Invoke the method using the required column as an argument.

```csharp
private void Button_Clicked(object sender, EventArgs e)
{
    // Access the desired column; adjust the index as needed.
    var column = this.grid.Columns[3];

    // Use reflection to get the internal ScrollColumnIntoView method.
    MethodInfo getScrollToColumn = this.grid.GetType().GetMethod("ScrollColumnIntoView", BindingFlags.Instance | BindingFlags.NonPublic);

    // Invoke the method to scroll the specified column into view.
    getScrollToColumn.Invoke(this.grid, new object[] { column });
}
```

## See Also

- [DataGrid for MAUI Overview](https://docs.telerik.com/devtools/maui/controls/datagrid/overview)
- [Reflection in C#](https://learn.microsoft.com/en-us/dotnet/fundamentals/reflection/reflection)
