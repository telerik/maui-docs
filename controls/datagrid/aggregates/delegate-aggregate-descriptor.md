---
title: Delegate Aggregate Descriptor
page_title: .NET MAUI DataGrid Documentation - Delegate Aggregate Descriptor
description: Learn how to define property look-up logic and a custom function applied over the property values of the Telerik UI for .NET MAUI DataGrid by using the DelegateAggregateDescriptor, and accumulate an aggregated result based on the component data.
position: 2
previous_url: /controls/datagrid/aggregates/DelegateAggregateDescriptor
slug: datagrid-delegate-aggregate-descriptor
---

# .NET MAUI DataGrid Delegate Aggregate Descriptor

The `DelegateAggregateDescriptor` allows you to define property lookup logic and a custom function that are applied over the property values of the [.NET MAUI DataGrid]({%slug datagrid-overview%}), which accumulates an aggregated result based on the component data.

To set up the `DelegateAggregateDescriptor`, use the following properties:

* `ValueLookup`&mdash;Defines an `IKeyLookup` instance, which retrieves the value from the underlying `ViewModel` that is used for computing the aggregated value.
* `Function`&mdash;Defines an `IAggregateFunction` instance that performs the aggregation of the values as specified by the `ValueLookup` property.
* `Format`&mdash;Defines the string format that will be applied over the aggregated value.

The following example uses the `DelegateAggregateDescriptor` and a custom implementation for a `SumIf` function which sums the values in a range that meet a certain criteria:

**1.** Create a class that inherits from the `IKeyLookup` interface. It will return the values of a `Price` property declared in our business model that is of type `double`.

<snippet id='datagrid-delegate-aggregate-key'/>

**2.** Declare a class that inherits from the `IAggregateFunction` interface. This class will contain our logic for the `SumIf` function which we will later implement through XAML:

<snippet id='datagrid-delegate-aggregate-function'/>

**3.** Declare the `DelegateAggregateDescriptor` in XAML.

<snippet id='datagrid-property-delegate-descriptor-example'/>

**4.** Define a sample data:

<snippet id='datagrid-aggregates-model'/>

**5.** Set a source to the `RadDataGrid.ItemsSource` proeprty:

<snippet id='datagrid-gelegate-aggregate-source'/>

The following image shows the end result.

![Delegate Aggregate Descriptor](../images/datagrid-delegate-aggregate-windows.png)

>important For DataGrid `DelegateAggregateDescriptor` example refer to the [SDKBrowser Demo application]({%slug sdkbrowser-app%}) and navigate to the **DataGrid > Aggregates** category.

## See Also

- [Property Aggregate Descriptor]({%slug datagrid-property-aggregate-descriptor%})
