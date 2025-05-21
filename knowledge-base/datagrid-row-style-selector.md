---
title: Apply Row Background Style Selector in the Telerik UI for .NET MAUI DataGrid
description: Style the rows, alternate rows and row details using style selector in MAUI DataGrid control.
type: how-to
page_title: Row Style Selector in DataGrid
slug: datagrid-row-style-selector
position: 5
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.0.0 | Telerik UI for .NET MAUI DataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 


## Description

This how-to article describes how to style the alternate rows, rows and row details in the Telerik MAUI DataGrid by using the `RowBackgroundStyleSelector` property.

This KB article also answers the following questions:

* How to define a style to the row details that is different than the rows and alternate rows?
* How to apply conditional styling to the rows and alternate rows in the DataGrid control?
* Can I specify different styles to the DataGrid rows, alternate rows and row details?

## Solution

To define a style selector to the DataGrid rows you need to use the `RowBackgroundStyleSelector` property. 


To apply a `RowBackgroundStyleSelector` you have to:

**1.** Create a custom class `MyRowBackgroundStyleSelector` that inherits from `IStyleSelector`.
**2.** Implement the `SelectStyle` method.

```C#
public class MyRowBackgroundStyleSelector : IStyleSelector
{
    public Style RowBackgroundStyle { get; set; }

    public Style AlternateRowBackgroundStyle { get; set; }

    public Style RowDetailsBackgroundStyle { get; set; }

    public Style AlternateRowDetailsBackgroundStyle { get; set; }

    public Style SelectStyle(object item, BindableObject bindable)
    {
        if (item is DataGridRowInfo rowInfo)
        {
            // In case you want to style the row background based on the business object associated with the row.
            var myitem = rowInfo.Item as MyData;

            if (rowInfo.IsRowDetails)
            {
                return this.RowDetailsBackgroundStyle;
            }

            else
            {
                if (rowInfo.IsAlternate)
                {
                    return this.AlternateRowBackgroundStyle;
                }
                else
                {
                    return this.RowBackgroundStyle;
                }
            }
        }

        return null;
    }
}
```

**4.** Create a sample data model:

<snippet id='datagrid-rowbackground-styleselector-model'/>

**5.** Define the `ViewModel`:

<snippet id='datagrid-rowbackground-styleselector-viewmodel'/>

**6.** Define the `RadDataGrid` in XAML:

<snippet id='datagrid-rowbackground-styleselector-example'/>

**7.** Add `MyRowBackgroundStyleSelector` as resource in the **Resource** page of the application:

<snippet id='datagrid-rowbackground-styleselector'/>

## See Also

- [DataGrid for .NET MAUI]({%slug datagrid-overview%})
- [Style Selectors in DataGrid for .NET MAUI]({%slug datagrid-style-selectors%})