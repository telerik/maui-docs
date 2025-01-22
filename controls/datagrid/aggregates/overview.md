---
title: Overview
page_title: .NET MAUI DataGrid Documentation - Aggregate Overview
description: Learn more about the built-in aggregate functions of the Telerik UI for .NET MAUI DataGrid component.
position: 0
slug: datagrid-aggregates
---

# .NET MAUI DataGrid Aggregates

The DataGrid exposes an Aggregates API through its `DataGridColumn.AggregateDescriptors` collection, where you can add `PropertyAggregateDescriptor` and `DelegateAggregateDescriptor`.

{% if site.has_cta_panels == true %}
{% include cta-panel-maui-overview.html %}
{% endif %}

## Aggregate Descriptors

The [`PropertyAggregateDescriptor`]({%slug datagrid-property-aggregate-descriptor %}) enables you to use a set of available functions while the [`DelegateAggregateDescriptor`]({%slug datagrid-delegate-aggregate-descriptor %}) allows you to implement a custom function through the `IAggregateFunction` interface.

## Aggregates Visualization

Visualize the aggregates inside the:

* DataGrid Column Footer
* DataGrid Group Header
* DataGrid Group Footer

### Aggregates in Column Footer

Use the `ShowColumnFooters` property to visualize the [`ColumnFooters`]({%slug datagrid-column-footer %}) of the DataGrid. When applying aggregate descriptor(s) to the column, the aggregate results are displayed inside the column footer.

> The aggregate results are displayed inside the column footer only if there is no `FooterText` set.

![DataGrid Column Footer Aggregate](../images/datagrid-property-aggregate-windows.png)

### Aggregates in Group Header

When [grouping]({%slug datagrid-grouping-overview %}) is applied to the DataGrid, you can display the aggregate results for the groups data in the group header, next to the title of the group.

To show the Aggregates in the group header, set the `ShowGroupHeaderAggregates` to `True`.

![DataGrid Group Header Aggregate](../images/datagrid-group-header-aggregate.png)

To align the aggregates in the group according to its header set the `GroupAggregatesAlignment` (`enum` of type `Telerik.Maui.Controls.DataGrid.DataGridGroupAggregatesAlignment`) property. The available options are:

* (default)`None`&mdash;Aggregates are not aligned to the DataGrid columns. The aggregates results are displayed after the text displayed for the group key.
* `NextToHeader`&mdash;Aggregate results are aligned to the DataGrid columns and placed next to the header of the group.

### Aggregates in Group Footer

When [grouping]({%slug datagrid-grouping-overview %}) is applied to the DataGrid, you can display the aggregate results for the groups data in the group footer.

To visualize the group footer, set the `ShowGroupFooters` property to `True`. The group footer is divided into cells which are aligned with the respective columns and show the aggregate results for the particular column.

![DataGrid Group Footer Aggregate](../images/datagrid-group-footer-aggregate.png)

>tip For an outline of all DataGrid features review the [.NET MAUI DataGrid Overview]({%slug datagrid-overview%}) article.

## See Also

- [Property Aggregate Descriptor]({%slug datagrid-property-aggregate-descriptor%})
- [Delegate Aggregate Descriptor]({%slug datagrid-delegate-aggregate-descriptor%})
