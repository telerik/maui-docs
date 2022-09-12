---
title: Overview
page_title: .NET MAUI DataGrid Documentation - Aggregate Overview
description: "Review the Telerik .NET MAUI DataGrid Aggregates documentation article to learn more about all built in Aggregate functions you can use."
position: 0
slug: datagrid-aggregates
---

# Overview

The DataGrid exposes an Aggregates API through the `DataGridColumn.AggregateDescriptors` property where you can add PropertyAggregateDescriptors or DelegateAggregateDescriptors.

The [PropertyAggregateDescriptor]({%slug datagrid-property-aggregate-descriptor %}) enables you to utilize a set of available functions, while the [DelegateAggregateDescriptor]({%slug datagrid-delegate-aggregate-descriptor %}) allows you to implement a custom function through the `IAggregateFunction` interface.

The Telerik UI for .NET MAUI DataGrid Aggregates can be placed in the `ColumnFooter` as well as the `GroupHeader` and  `GroupFooter`. 

The `ShowColumnFooters` property is used to visualize the [ColumnFooters]({%slug datagrid-column-footer %}) of the `DataGrid`. However it is also used to display the Aggregates for the columns.

![DataGrid Column Footer Aggregate](images/datagrid-column-footer-aggregate.png)

> The Aggregates are displayed only if there is no FooterText set.

When [Grouping]({%slug datagrid-grouping-overview %}) is applied you can display the aggregate results for the group's data in the `Group Footer`. In order to visualize the footer the `ShowGroupFooters` property needs to be set to True. The Group footer is divided into cells which are aligned with the respective columns and show the aggregate results for the particular column.

![DataGrid Group Footer Aggregate](images/datagrid-group-footer-aggregate.png)

The aggregate results can also be visualized in the Group header next to the title of the group. In order to show the Aggregates in the Header of the group the `ShowGroupHeaderAggregates` needs to be set to True.

![DataGrid Group Header Aggregate](images/datagrid-group-header-aggregate.png)

## See Also

- [Property Aggregate Descriptor]({%slug datagrid-property-aggregate-descriptor%})
- [Delegate Aggregate Descriptor]({%slug datagrid-delegate-aggregate-descriptor%})