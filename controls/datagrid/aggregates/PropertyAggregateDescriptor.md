---
title: Property Aggregate Descriptor
page_title: .NET MAUI DataGrid Documentation - Property Aggregate Descriptor
description: Check our Property Aggregate Descriptor documentation article for Telerik DataGrid for .NET MAUI control.
position: 1
slug: datagrid-property-aggregate-descriptor
---

# PropertyAggregateDescriptor

The `PropertyAggregateDescriptor` allows you to define a property and a function that are applied over the property values of the DataGrid, which accumulates an aggregated result based on the component data.

To set up the `PropertyAggregateDescriptor`, use the following properties:
* `PropertyName`&mdash;Defines the name of the property that is used to compute the aggregate value.
* `Function`&mdash;Defines a KnownFunction value that will be applied to the aggregate.
* `Caption`&mdash;Defines the caption of the aggregate. You can use `Caption` to display text in the UI when the `AggregatesTemplate` is set.
* `Format`&mdash;Defines the string format that will be applied over the aggregated value.

The following example shows how to add a `PropertyAggregateDescriptor` to the DataGrid. It will take the values from the `Name`, `Price`, `DeliveryPrice` and `Quantity` properties of the row model and the result will be the `Min` and `Max` prices as well as `Average` price for delivery and the `Count` of the listed items.

<snippet id="datagrid-property-aggregate-descriptor-example">

## See Also

- [Delegate Aggregate Descriptor]({%slug datagrid-delegate-aggregate-descriptor%})