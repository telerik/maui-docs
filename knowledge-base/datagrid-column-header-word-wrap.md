---
title: Enabling Word Wrapping for Column Headers in DataGrid for UI for .NET MAUI
description: Learn how to enable word wrapping for column headers in DataGrid for UI for .NET MAUI by using a header template.
type: how-to
page_title: How to Enable Word Wrapping in DataGrid Column Headers for UI for .NET MAUI
meta_title: How to Enable Word Wrapping in DataGrid Column Headers for UI for .NET MAUI
slug: datagrid-column-header-word-wrap
tags: datagrid, ui for .net maui, column header, wordwrap, template
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.1.0 | Telerik UI for .NET MAUI DataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

I want to enable word wrapping for the column header text in the [DataGrid for UI for .NET MAUI](https://www.telerik.com/maui-ui/documentation/controls/datagrid/overview). This feature allows text in the header to wrap to the next line when it exceeds the width of its container.

This knowledge base article also answers the following questions:
- How do I apply word wrapping in DataGrid column headers?
- Can I use a template for DataGrid column headers in UI for .NET MAUI?
- How to format text in a DataGrid column header?

## Solution

To enable word wrapping for column headers, use a template for the `HeaderContentTemplate` property of a `DataGridTextColumn`. The template allows customization of the header's appearance, including enabling word wrapping for text.

### Example in XAML

```xml
<telerik:DataGridTextColumn.HeaderStyle>
    <Style TargetType="telerik:DataGridColumnHeaderAppearance">
        <Setter Property="BackgroundColor" Value="#00796B" />
        <Setter Property="SortIndicatorColor" Value="#FFFFFF" />
        <Setter Property="FilterIndicatorTextColor" Value="#99FFFFFF" />
        <Setter Property="FilterIndicatorActiveTextColor" Value="#80CBC4" />
    </Style>
</telerik:DataGridTextColumn.HeaderStyle>
<telerik:DataGridTextColumn.HeaderContentTemplate>
    <DataTemplate>
        <Label Text="Capital fsfsgsd fsdfsdfsdfsd" 
               FontSize="20" 
               FontAttributes="Bold" 
               LineBreakMode="WordWrap" 
               HorizontalTextAlignment="Center" 
               VerticalTextAlignment="Center" />
    </DataTemplate>
</telerik:DataGridTextColumn.HeaderContentTemplate>
```

### Example in C#

```csharp
var headerTemplate = new DataTemplate(() =>
{
    var label = new Label
    {
        Text = "Hello gregreg g re gre g reg re g",
        FontSize = 20,
        FontAttributes = FontAttributes.Bold,
        LineBreakMode = LineBreakMode.WordWrap,
        HorizontalTextAlignment = TextAlignment.Center,
        HorizontalOptions = LayoutOptions.Fill,
        VerticalTextAlignment = TextAlignment.Center,
        Margin = new Thickness(4, 0)
    };

    return label;
});

var nameColumn = new DataGridTextColumn
{
    PropertyName = nameof(Models.Person.Name),
    HeaderText = "Name",
    HeaderContentTemplate = headerTemplate
};
dataGrid.Columns.Add(nameColumn);
```

### Notes

When using a template, it overrides the properties set in the `HeaderStyle` for the text. Define properties such as font size, font attributes, and text color directly in the label inside the template.

## See Also

- [DataGrid Column Header Styling](https://www.telerik.com/maui-ui/documentation/controls/datagrid/theming-and-styles/columns-styling#header-styling)
- [Customizing DataGrid Columns](https://www.telerik.com/maui-ui/documentation/controls/datagrid/columns/overview)
