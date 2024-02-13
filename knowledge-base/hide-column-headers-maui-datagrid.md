---
title: How to Hide Column Headers in a DataGrid for MAUI
description: Learn how to hide the column headers in a DataGrid for .NET MAUI.
type: how-to
page_title: Hide Column Headers in DataGrid for MAUI
slug: hide-column-headers-maui-datagrid
tags: maui, datagrid, column-headers, hide
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 6.7.0 | Telerik UI for .NET MAUI DataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

## Description

I want to hide the column headers in a DataGrid for MAUI. Is there a way to achieve this?

## Solution

To hide the column headers in a DataGrid for MAUI, you can use the `ColumnHeaderStyle` property and customize the style of the column headers. Follow these steps:

1. If you use C#, create a new instance of the `DataGridColumnHeaderStyle` class and set the following properties:
   - `TextFontSize` to 0
   - `FilterIndicatorFontSize` to 0
   - `BackgroundColor` to `Colors.Transparent`
   - `BorderColor` to `Colors.Transparent`
   - `BorderThickness` to a new `Thickness` with a value of 0.

   Here's an example:

   ```csharp
   var dataGrid = new RadDataGrid();
   dataGrid.ItemsSource = new List<Data>
   {
       new Data { Country = "India", Capital = "New Delhi"},
       new Data { Country = "South Africa", Capital = "Cape Town"},
       new Data { Country = "Nigeria", Capital = "Abuja" },
       new Data { Country = "Singapore", Capital = "Singapore" }
   };
   dataGrid.AutoGenerateColumns = false;
   var headerStyle = new DataGridColumnHeaderStyle
   {
       TextFontSize = 0,
       FilterIndicatorFontSize = 0,
       BackgroundColor = Colors.Transparent,
       BorderColor = Colors.Transparent,
       BorderThickness = new Thickness(0),
   };
   var column1 = new DataGridTextColumn { PropertyName = "Country" };
   column1.HeaderStyle = headerStyle;

   dataGrid.Columns.Add(column1);
   ```

2. If you use XAML code, add the `HeaderStyle` property to the `DataGridTextColumn` and set its value to a new instance of `DataGridColumnHeaderStyle` with the following properties:
   - `BackgroundColor` to `"Transparent"`
   - `BorderColor` to `"Transparent"`
   - `FilterIndicatorFontSize` to `0`
   - `TextFontSize` to `0`
   - `BorderThickness` to a new `Thickness` with a value of 0.

   Here's an example:

   ```xaml
   <telerik:RadDataGrid>
       <telerik:RadDataGrid.Columns>
           <telerik:DataGridTextColumn PropertyName="Country">
               <telerik:DataGridTextColumn.HeaderStyle>
                   <telerik:DataGridColumnHeaderStyle BackgroundColor="Transparent" BorderThickness="0"
                                                       BorderColor="Transparent"
                                                       FilterIndicatorFontSize="0"
                                                       TextFontSize="0"/>
               </telerik:DataGridTextColumn.HeaderStyle>
           </telerik:DataGridTextColumn>
       </telerik:RadDataGrid.Columns>
   </telerik:RadDataGrid>
   ```

By customizing the column header style and setting the font size to 0 and the color to transparent, you can effectively hide the column headers in the DataGrid for .NET MAUI.
