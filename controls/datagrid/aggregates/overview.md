---
title: Overview
page_title: .NET MAUI DataGrid Documentation - Aggregate Overview
description: Review the Telerik .NET MAUI DataGrid Aggregates documentation article to learn more about all built in Aggregate functions you can use.
position: 0
slug: datagrid-aggregates
---

# Overview

The DataGrid exposes an Aggregates API through the `RadDataGrid.AggregateDescriptors` property where you can add PropertyAggregateDescriptors or DelegateAggregateDescriptors.

The PropertyAggregateDescriptor enables you to utilize a set of available functions, while the `DelegateAggregateDescriptor` allows you to implement a custom function through the `IAggregateFunction` interface.

The Telerik UI for .NET MAUI DataGrid Aggregates can be placed in the `DataGrid Footer` as well as the `GroupHeader`, `GroupFooter` and `ColumnFooter`

The `PropertyAggregateDescriptor` supports the following `KnownFunction` aggregates:

* `Sum` - The `Sum` function sumarizes all values in the column.
* `Min` - The `Minimum` value of the cells in the column.
* `Max` - The `Maximum` value of the cells in the column.
* `Average` - The `Average` value of the cells in the column.
* `Count` - The `COUNT` function counts the items in the column.
* `Product` - The `PRODUCT` function multiplies all the numbers given as arguments and returns the product.
* `StdDev` - The `Standard Deviation` is a measure of how widely values are dispersed from the average value, based on a sample function.
* `StdDevP` - The `Standard Deviation` is a measure of how widely values are dispersed from the average value, based on the entire population function.
* `Var` - The `Variance` is a measure of dispersion, based on a sample function.
* `VarP` - The `Variance` is a measure of dispersion, based on the entire population function.

> The Aggregates are displayed only if there is no FooterText set.

## See Also

- [Property Aggregate Descriptor]({%slug datagrid-property-aggregate-descriptor%})
- [Delegate Aggregate Descriptor]({%slug datagrid-delegate-aggregate-descriptor%})