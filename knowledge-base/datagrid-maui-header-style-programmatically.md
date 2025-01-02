---
title: Setting the DataGrid Header Style Programmatically in MAUI When Using the GenerateColumnCommand
description: Learn how to programmatically define the header style of a DataGrid component in MAUI applications.
type: how-to
page_title: Programmatically Styling DataGrid Headers in MAUI
slug: datagrid-maui-header-style-programmatically
tags: datagrid, maui, header, style, programmatically, column, generate columns command
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 9.0.0 | Telerik UI for .NET MAUI DataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

## Description
How can I programmatically set the style of a DataGrid header, for example, setting the font to bold when using a custom command to generate the columns?

This knowledge base article also answers the following questions:
- How to change the DataGrid header font family in MAUI programmatically?
- How to set the DataGrid header border thickness in MAUI?
- How to apply a custom style to DataGrid headers in MAUI applications?

## Solution

To programmatically set the style of the DataGrid header, create a new `Style` instance targeting `DataGridColumnHeaderAppearance`. Add `Setter` instances to the style to define properties such as `TextFontFamilyProperty` and `BorderThicknessProperty`. Assign this style to the `HeaderStyle` property of the column in the `Execute` method of your `CustomGenerateColumnCommand`.

```csharp
Style style = new Style(typeof(DataGridColumnHeaderAppearance));
style.Setters.Add(new Setter() 
{ 
    Property = DataGridColumnHeaderAppearance.TextFontFamilyProperty, 
    Value="Helvetica"
});
style.Setters.Add(new Setter() 
{ 
    Property = DataGridColumnHeaderAppearance.BorderThicknessProperty, 
    Value = new Microsoft.Maui.Thickness(1) 
});
// Add more setters as needed.
...
context.Result.HeaderStyle = style;
```

For detailed information on styling the DataGrid columns, refer to the [DataGrid Columns Styling](https://docs.telerik.com/devtools/maui/controls/datagrid/theming-and-styles/columns-styling) article in the Telerik MAUI documentation.

## See Also
- [DataGrid Overview](https://docs.telerik.com/devtools/maui/controls/datagrid/overview)
- [DataGrid Theming and Styles](https://docs.telerik.com/devtools/maui/controls/datagrid/theming-and-styles)
