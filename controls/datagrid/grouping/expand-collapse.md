---
title: Expand and Collapse Groups
page_title: .NET MAUI DataGrid Documentation - Expand and Collapse
description: "Review the Telerik .NET MAUI DataGrid Grouping Expand and Collapse documentation article to learn more about the Expand and Collapse functions you can use."
position: 6
slug: datagrid-expand-collapse
---

# Expand and Collapse Groups in .NET MAUI DataGrid

The DataGrid supports group expand and collapse operations either through the UI by tapping on the group headers, or programmatically. By default, all the groups are expanded.

This section provides an overview of the methods and commands used to control the expand/collapse state of the DataGrid groups.

## Get the Grouped DataGrid Items

To manipulate the collapsible DataGrid groups, first you will need to call its `GetDataView` method. In short, the `GetDataView` method provides a view of the `ItemsSource` after all the sorting, grouping, and filtering operations are applied. The return type is `IDataViewCollection` which exposes the `expand` and `collapse` methods described in the following sections.

```C#
var dataView = this.dataGrid.GetDataView();
```

## Expand and Collapse All Groups

To expand all groups, use the `ExpandAll` method and, respectively, the `CollapseAll` method to collapse all groups.

```C#
//expand all
var dataView = this.dataGrid.GetDataView();
dataView.ExpandAll();

//collapse all
var dataView = this.dataGrid.GetDataView();
dataView.CollapseAll();
```

## Expand and Collapse Specific Groups

You can retrieve the first-level groups through the `GetGroups` method of the `IDataViewCollection` object and use `ExpandGroup`/`CollapseGroup` to make a certain group to expand or collapse respectively. You can check whether a group is expanded trough the `GetIsExpanded` method.

The following example demonstrates how these methods are used:

```C#
var dataView = this.dataGrid.GetDataView();
var rootGroups = dataView.GetGroups();

var isFirstExpanded = dataView.GetIsExpanded(rootGroups.First());
//expand a certain group
dataView.ExpandGroup(rootGroups.First());
//collapse a certain group
dataView.CollapseGroup(rootGroups.First());
```

Additionally, `IDataViewCollection` provides the `ExpandItem`/`CollapseItem` methods that take a data item as a parameter and expand/collapse the immediate group containing this item.

```C#
var lastItem = (dataGrid.ItemsSource as IEnumerable<City>).Last();
var dataView = this.dataGrid.GetDataView();
dataView.CollapseItem(lastItem);
```

## See Also

- [Property Group Descriptor]({%slug datagrid-property-group-descriptor%})
- [Delegate Group Descriptor]({%slug datagrid-delegate-group-descriptor%})