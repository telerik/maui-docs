---
title: How to Hide Column Headers in a DataGrid for MAUI
description: Learn how to hide the column headers in a Telerik UI for .NET MAUI DataGrid.
type: how-to
page_title: Hide Column Headers in DataGrid for MAUI
slug: hide-column-headers-maui-datagrid
tags: maui, datagrid, column-headers, hide
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 13.1.0 | Telerik UI for .NET MAUI DataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

## Description

I want to hide the column headers in a DataGrid for MAUI. Is there a way to achieve this?

## Solution

To hide the column headers in a DataGrid for .NET MAUI, you can use the `ColumnHeaderStyle` property and customize the style of the column headers by setting the `FontSize` to `0` and the `Color` to `Transparent`. 

Here is an example:

1. If you are using C#, create a new instance of the `DataGridColumnHeaderStyle` class and set the following properties:
   - `TextFontSize` to 0
   - `FilterIndicatorFontSize` to 0
   - `BackgroundColor` to `Colors.Transparent`
   - `BorderColor` to `Colors.Transparent`
   - `BorderThickness` to a new `Thickness` with a value of 0.

   The `HeaderStyle` customization in C#:

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
   var headerStyle = new Style(typeof(DataGridColumnHeaderAppearance));
   headerStyle.Setters.Add(new Setter { Property = DataGridColumnHeaderAppearance.TextFontSizeProperty, Value = 0 });
   headerStyle.Setters.Add(new Setter { Property = DataGridColumnHeaderAppearance.FilterIndicatorFontSizeProperty, Value = 0 });
   headerStyle.Setters.Add(new Setter { Property = DataGridColumnHeaderAppearance.BackgroundColorProperty, Value = Colors.Transparent });
   headerStyle.Setters.Add(new Setter { Property = DataGridColumnHeaderAppearance.BorderColorProperty, Value = Colors.Transparent });
   headerStyle.Setters.Add(new Setter { Property = DataGridColumnHeaderAppearance.BorderThicknessProperty, Value = new Thickness(0) });

   var column1 = new DataGridTextColumn { PropertyName = "Country" };
   column1.HeaderStyle = headerStyle;

   dataGrid.Columns.Add(column1);
   ```

2. If you are using XAML code, add the `HeaderStyle` property to the `DataGridTextColumn` and set its value to a new instance of `DataGridColumnHeaderStyle` with the following properties:
   - `BackgroundColor` to `"Transparent"`
   - `BorderColor` to `"Transparent"`
   - `FilterIndicatorFontSize` to `0`
   - `TextFontSize` to `0`
   - `BorderThickness` to a new `Thickness` with a value of 0.

   The `HeaderStyle` customization in XAML:

   ```xaml
   <telerik:RadDataGrid>
       <telerik:RadDataGrid.Columns>
           <telerik:DataGridTextColumn PropertyName="Country">
                <telerik:DataGridTextColumn.HeaderStyle>
                    <Style TargetType="telerik:DataGridColumnHeaderAppearance">
                        <Setter Property="TextFontSize" Value="0" />
                        <Setter Property="FilterIndicatorFontSize" Value="0" />
                        <Setter Property="BackgroundColor" Value="Transparent" />
                        <Setter Property="BorderColor" Value="Transparent" />
                        <Setter Property="BorderThickness" Value="0" />
                    </Style>
                </telerik:DataGridTextColumn.HeaderStyle>
           </telerik:DataGridTextColumn>
       </telerik:RadDataGrid.Columns>
   </telerik:RadDataGrid>
   ```
