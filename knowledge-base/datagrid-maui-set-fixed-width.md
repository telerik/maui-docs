---
title: Setting Fixed Width for DataGrid and Its Columns in .NET MAUI App
description: Learn how to specify the width of a DataGrid and its columns in a MAUI application by using the WidthRequest and Width properties.
type: how-to
page_title: How to Define Fixed Width for MAUI DataGrid and Columns
slug: datagrid-maui-set-fixed-width
tags: datagrid, width, columns, fixed, maui
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 7.1.0 | Telerik UI for .NET MAUI DataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I need to set a specific width for the DataGrid and its columns in a MAUI application. It's essential for the columns to maintain a fixed width, disregarding the content size. This KB article also answers the following questions:

- How to set fixed width for DataGrid columns in MAUI?
- How to adjust the DataGrid size in MAUI?
- Can I specify exact column widths for a DataGrid in MAUI?

## Solution

To set a fixed width for both the [DataGrid]({%slug datagrid-overview%}) and its columns in a MAUI application, follow these steps:

1. Set the `SizeMode` property of each column to `Fixed`. This ensures that the columns will not adjust their width based on their content.
2. Specify the desired width for each column using the `Width` property.
3. Adjust the DataGrid's width by setting the `WidthRequest` property at the DataGrid level.

Here is an example demonstrating how to configure the DataGrid and its columns with fixed widths:

```XAML
<telerik:RadDataGrid x:Name="grid" AutoGenerateColumns="False" WidthRequest="300">
    <telerik:RadDataGrid.Columns>
        <telerik:DataGridTextColumn PropertyName="Country" HeaderText="Country" Width="100" SizeMode="Fixed"/>
        <telerik:DataGridTextColumn PropertyName="Capital" HeaderText="Capital" Width="200" SizeMode="Fixed"/>
    </telerik:RadDataGrid.Columns>
</telerik:RadDataGrid>
```

In this setup, the DataGrid will have a total width of 300 units, while the columns for "Country" and "Capital" will have fixed widths of 100 and 200 units, respectively.

## See Also

- [DataGrid Overview]({%slug datagrid-overview%})
- [DataGrid Columns Width Documentation]({%slug datagrid-columns-width%})
