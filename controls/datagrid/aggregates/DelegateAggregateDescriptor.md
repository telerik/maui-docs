---
title: Delegate Aggregate Descriptor
page_title: .NET MAUI DataGrid Documentation - Delegate Aggregate Descriptor
description: Check our Delegate Aggregate Descriptor documentation article for Telerik DataGrid for .NET MAUI control.
position: 2
slug: datagrid-delegate-aggregate-descriptor
---

# DelegateAggregateDescriptor

The `DelegateAggregateDescriptor` allows you to define property look-up logic and a custom function that are applied over the property values of the DataGrid, which accumulates an aggregated result based on the component data.

To set up the `DelegateAggregateDescriptor`, use the following properties:

* `ValueLookup`&mdash;Defines an `IKeyLookup` instance, which retrieves the value from the underlying `ViewModel` that is used for computing the aggregated value.
* `Function`&mdash;Defines an `IAggregateFunction` instance that performs the aggregation of the values as specified by the `ValueLookup` property.
* `Format`&mdash;Defines the string format that will be applied over the aggregated value.

The following example shows how to implement the `IKeyLookup` and `IAggregateFunction` and use them with the `DelegateAggregateDescriptor`. 

1. First, create a class that inherits from the `IKeyLookup` interface. It will return the values of a Price property declared in our business model that is of type double.

<snippet id="datagrid-delegate-aggregate-key">

2. Then, implement a class that inherits from the `IAggregateFunction` interface. This function will return half of the maximum value of the `Price` property and round it to the closest whole number.

<snippet id="datagrid-delegate-aggregate-function">

3. Declare the `DelegateAggregateDescriptor` in XAML.

<snippet id="datagrid-property-delegate-descriptor-example">

## See Also

- [Property Aggregate Descriptor]({%slug datagrid-property-aggregate-descriptor%})