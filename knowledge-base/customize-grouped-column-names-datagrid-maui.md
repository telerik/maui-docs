---
title: Customizing the Column Name inside the DataGrid Grouping Panel
description: Learn how to assign custom names to grouped columns in the DataGrid for MAUI.
type: how-to
page_title: How to Assign Friendly Names to Grouped Columns in MAUI DataGrid Grouping Panel
slug: customize-grouped-column-names-datagrid-maui
tags: datagrid, maui, grouping, custom name, PropertyGroupDescriptor, DisplayContent
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 9.0.0 | Telerik UI for .NET MAUI DataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

## Description

When grouping columns in the DataGrid for MAUI, the default behavior displays the actual property name in the grouping panel. This article demonstrates how to customize this name to a more user-friendly one. 

This knowledge base article also answers the following questions:
- How to change the displayed name of a grouped column in DataGrid for MAUI?
- How to set a custom name for the grouping panel in DataGrid for MAUI?
- How to use `DisplayContent` to customize grouped column names in MAUI DataGrid?

## Solution

To customize the name displayed for a grouped column in the DataGrid Grouping Panel for MAUI, utilize the `DisplayContent` property of the `PropertyGroupDescriptor`. This property allows you to specify a custom name that will be shown in the grouping panel instead of the default property name.

The following example demonstrates how to set a custom name for a column grouped by the `TimeStamp` property:

```xml
<telerik:PropertyGroupDescriptor PropertyName="TimeStamp" DisplayContent="Creation Time" />
```

In this example, columns grouped by the `TimeStamp` property will display `Creation Time` in the DataGrid's grouping panel, providing a more user-friendly name for the grouping.

## See Also

- [Grouping in DataGrid for MAUI]({%slug datagrid-grouping-overview%})
- [DataGrid Overview for MAUI]({%slug datagrid-overview%})
