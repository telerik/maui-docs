---
title: Overview
page_title: .NET MAUI DataGrid Documentation - Aggregate Overview
description: Learn more about the built-in aggregate functions of the Telerik UI for .NET MAUI DataGrid component.
position: 0
slug: datagrid-aggregates
---

# .NET MAUI DataGrid Aggregates

The DataGrid exposes an Aggregates API through its `DataGridColumn.AggregateDescriptors` property where you can add `PropertyAggregateDescriptors` or `DelegateAggregateDescriptors`.

{% if site.has_cta_panels == true %}
{% include cta-panel-overview.html %}
{% endif %}

The [`PropertyAggregateDescriptor`]({%slug datagrid-property-aggregate-descriptor %}) enables you to use a set of available functions while the [`DelegateAggregateDescriptor`]({%slug datagrid-delegate-aggregate-descriptor %}) allows you to implement a custom function through the `IAggregateFunction` interface.

The Telerik UI for .NET MAUI DataGrid Aggregates can be placed in the `ColumnFooter` as well as the `GroupHeader` and  `GroupFooter`.

The `ShowColumnFooters` property is used to visualize the [`ColumnFooters`]({%slug datagrid-column-footer %}) of the DataGrid and is also used to display the Aggregates for the columns.

> The Aggregates are displayed only if there is no `FooterText` set.

![DataGrid Column Footer Aggregate](../images/datagrid-property-aggregate-windows.png)

When [grouping]({%slug datagrid-grouping-overview %}) is applied to the DataGrid, you can display the aggregate results for the groups data in the group footer. To visualize the footer, set the `ShowGroupFooters` property to `True`. The group footer is divided into cells which are aligned with the respective columns and show the aggregate results for the particular column.

![DataGrid Group Footer Aggregate](../images/datagrid-group-footer-aggregate.png)

The aggregate results can also be visualized in the group header next to the title of the group. To show the Aggregates in the group header, set the `ShowGroupHeaderAggregates` to `True`.

![DataGrid Group Header Aggregate](../images/datagrid-group-header-aggregate.png)

## See Also

- [Property Aggregate Descriptor]({%slug datagrid-property-aggregate-descriptor%})
- [Delegate Aggregate Descriptor]({%slug datagrid-delegate-aggregate-descriptor%})
