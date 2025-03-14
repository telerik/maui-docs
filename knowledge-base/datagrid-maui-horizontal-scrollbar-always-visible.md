---
title: Displaying the Horizontal Scrollbar in DataGrid for MAUI on Windows
description: Learn how to make the horizontal scrollbar always visible in the DataGrid for MAUI on Windows.
type: how-to
page_title: How to Ensure the Horizontal ScrollBar is Always Visible in MAUI DataGrid on Windows
slug: datagrid-maui-horizontal-scrollbar-always-visible
tags: datagrid, maui, windows, scrollbar, visibility
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 10.0.0 | Telerik UI for .NET MAUI ComboBox | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

In a MAUI application, the horizontal scrollbar within the DataGrid on the Windows platform may not be visible by default. This behavior is observed when the DataGrid's content width does not exceed the application window's width. 

This knowledge base article also answers the following questions:
- How to make the horizontal scrollbar always visible in the DataGrid for MAUI on Windows?
- What code adjustments are needed to ensure scrollbar visibility in a MAUI DataGrid?
- Can the horizontal scrollbar visibility be controlled programmatically in MAUI DataGrid for Windows?

## Solution

To ensure that the horizontal scrollbar is always visible in the DataGrid for MAUI on Windows, regardless of the content width, follow these steps:

1. Subscribe to the `Loaded` event of the DataGrid.
2. Use the event handler to access the `RadScrollView` component of the DataGrid.
3. Set the `HorizontalScrollBarVisibility` property to `Visible` for the scroll view on the Windows platform.

Below is the code snippet demonstrating how to achieve this:

```csharp
#if WINDOWS
private void DataGrid_Loaded(object sender, System.EventArgs e)
{
    foreach (var child in ((RadDataGrid)sender).Children)
    {
        if (child is RadScrollView)
        {
            if (child.Handler?.PlatformView is Telerik.Maui.Platform.RadMauiScrollView sv)
            {
                sv.HorizontalScrollBarVisibility = Microsoft.UI.Xaml.Controls.ScrollBarVisibility.Visible;
            }
        }
    }
}
#endif
```

Ensure this code snippet is placed in the code-behind of the page where your DataGrid is located. Also, make sure that the `Loaded` event of the DataGrid is properly subscribed to invoke this method.

## See Also

- [DataGrid Overview]({%datagrid-overview%})
