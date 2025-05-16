---
title: Programmatic Filtering
page_title: .NET MAUI TreeDataGrid Documentation - Programmatic Filtering
description: Learn how to apply an external filter to the TreeDataGrid for .NET MAUI by disabling the built-in filtering UI and programmatically filter tha data in the tree grid.
position: 3
slug: treedatagrid-programmatic-filtering
---

# Programmatic Filtering

Programmatic filtering allows you to implement external filtering—for example, by disabling the built-in filtering UI and applying filters directly in code.

Programmatic Filtering is achieved by adding different filter descriptors in the `FilterDescriptor` collection of the [.NET MAUI TreeDataGrid]({%slug treedatagrid-overview%}) control. 

The following descriptor types are supported:

- [.NET MAUI TreeDataGrid Filtering](#net-maui-treedatagrid-filtering)
  - [Filtering UI](#filtering-ui)
  - [FilterControl Template](#filtercontrol-template)
  - [Programmatic Filtering](#programmatic-filtering)
    - [Text Filter Descriptor](#text-filter-descriptor)
    - [Numerical Filter Descriptor](#numerical-filter-descriptor)
    - [DateTime Filter Descriptor](#datetime-filter-descriptor)
    - [TimeSpan Filter Descriptor](#timespan-filter-descriptor)
    - [Boolean Filter Descriptor](#boolean-filter-descriptor)
    - [Nested Property Text Filter Descriptor](#nested-property-text-filter-descriptor)
    - [Distinct Values Filter Descriptor](#distinct-values-filter-descriptor)
    - [Composite Filter Descriptor](#composite-filter-descriptor)
    - [Delegate Filter Descriptor](#delegate-filter-descriptor)

All `FilterDescriptors` are located in the `Telerik.Maui.Controls.Data` namespace.

When using C#, you need to add the using statement:

```C#
using Telerik.Maui.Controls.Data;
```

Alternatively, if using XAML, the filter descriptors are resolved through the same `telerik` xmlns:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

### Text Filter Descriptor

The `TextFilterDescriptor` supports the following properties:

* `PropertyName`&mdash;Gets or sets the name of the property that is used to retrieve the filter value.
* `Operator`&mdash;Gets or sets the `TextOperator` value that defines how the `Value` member is compared with each value from the items source.
* `Value`&mdash;Gets or sets the value used in the comparisons. This is the right operand of the comparison.
* `IsCaseSensitive`&mdash;Gets or sets a value that determines whether the text comparisons will be case-sensitive. The default value is `True`.

To use `TextFilterDescriptor`, you need to add its instance to the `RadDataGrid.FilterDescriptors` collection and to set its `PropertyName` property to associate it with the property from your custom objects. Then, through the `Operator` and `Value` properties, you need to set the filter condition and the value to compare. You can also use the `IsCaseSensitive` property to determine if the text comparisons will be case-sensitive or not.

```XAML
<telerik:TextFilterDescriptor PropertyName="Country"
                              Operator="StartsWith"
                              IsCaseSensitive="False"
                              Value="En"/>
```

### Numerical Filter Descriptor

The `NumericalFilterDescriptor` represents a descriptor which filters by properties of the `numerical` data type.

It exposes the following properties:

* `PropertyName`&mdash;Gets or sets the name of the property that is used to retrieve the filter value.
* `Value`&mdash;Gets or sets the value used in the comparisons. This is the right operand of the comparison.
* `Operator`&mdash;Gets or sets the `NumericalOperator` value that defines the boolean logic behind the left and right operand comparison.

```XAML
<telerik:NumericalFilterDescriptor PropertyName="StadiumCapacity"
                                   Operator="IsLessThan"
                                   Value="80000"/>
```

### DateTime Filter Descriptor

The `DateTimeFilterDescriptor` is a descriptor which filters by properties of the `System.DateTime` data type.

It exposes the following properties:

* `PropertyName`&mdash;Gets or sets the name of the property that is used to retrieve the filter value.
* `Value`&mdash;Gets or sets the value used in the comparisons. This is the right operand of the comparison.
* `Operator`&mdash;Gets or sets the `NumericalOperator` value that defines the boolean logic behind the left and right operand comparison.

```XAML
<telerik:DateTimeFilterDescriptor PropertyName="Established"
                                  Operator="IsLessThan"
                                  Value="1900/01/01"/>
```

### TimeSpan Filter Descriptor

The `TimeSpanFilterDescriptor` is a descriptor which filters by properties of the `System.TimeSpan` data type.

It exposes the following properties:

* `PropertyName`&mdash;Gets or sets the name of the property that is used to retrieve the filter value.
* `Value`&mdash;Gets or sets the value used in the comparisons. This is the right operand of the comparison.
* `Operator`&mdash;Gets or sets the `NumericalOperator` value that defines the boolean logic behind the left and right operand comparison.

```XAML
<telerik:TimeSpanFilterDescriptor PropertyName="Time"
                                  Operator="IsLessThan"
                                  Value="22/11/21"/>
```

### Boolean Filter Descriptor

The `BooleanFilterDescriptor` is a descriptor which filters by properties of the `System.Boolean` data type.

It exposes the following properties:

* `PropertyName`&mdash;Gets or sets the name of the property that is used to retrieve the filter value.
* `Value`&mdash;Gets or sets the value used in the comparisons. This is the right operand of the comparison.

```XAML
<telerik:BooleanFilterDescriptor PropertyName="IsChampion"
                                 Value="true"/>
```

### Nested Property Text Filter Descriptor

The `NestedPropertyTextFilterDescriptor` is a descriptor which allows you to filter the nested properties.

It exposes the following properties:

* `PropertyName`&mdash;Gets or sets the name of the property that is used to retrieve the filter value.
* `ItemPropertyGetter`&mdash;Sets a custom function that implements the access to the nested property. The function gets the value accessed by the `PropertyName` as an input argument and returns the nested property as an output result. If `ItemPropertyGetter` is not set, the filter descriptor behaves the same as [TextFilterDescriptor](#text-filter-descriptor).
* `Operator`&mdash;Gets or sets the `TextOperator` value that defines how the `Value` member is compared with each value from the items source.
* `Value`&mdash;Gets or sets the value used in the comparisons. This is the right operand of the comparison.
* `IsCaseSensitive`&mdash;Gets or sets a value that determines whether the text comparisons will be case-sensitive. The default value is `True`.

```C#
var filterDescriptor = new NestedPropertyTextFilterDescriptor();
filterDescriptor.PropertyName = "MyProperty";
filterDescriptor.Operator = Telerik.Maui.Controls.Data.TextOperator.EqualsTo;
filterDescriptor.Value = "Expected value";
filterDescriptor.ItemPropertyGetter = (originalPropertyValue) =>
{
    // The 'originalPropertyValue' is the object fetched by the 'PropertyName' of the descriptor. In this case, this is the value of 'MyProperty'.
    return ((MyChildObjectClass)originalPropertyValue).MyNestedProperty;
};
this.radTreeDataGrid.FilterDescriptors.Add(filterDescriptor);
```

### Distinct Values Filter Descriptor

The `DistinctValuesFilterDescriptor` is a descriptor which filters by distinct values.

It exposes the following properties:

* `PropertyName`&mdash;Gets or sets the name of the property that is used to retrieve the filter value.
* `Value`&mdash;Gets or sets the value used in the comparisons. This is the right operand of the comparison.

```XAML
<telerik:DistinctValuesFilterDescriptor PropertyName="Country" Value="Austria" />
```

### Composite Filter Descriptor

The `CompositeFilterDescriptor` represents a special `FilterDescriptorBase` that stores an arbitrary number of other descriptors instances. The logical `AND` or `OR` operator is applied upon all composed filters to determine the result of the `PassesFilter` routine.

```XAML
<telerik:CompositeFilterDescriptor Operator="And">
	<telerik:CompositeFilterDescriptor.Descriptors>
		<telerik:NumericalFilterDescriptor PropertyName="StadiumCapacity"
                                           Operator="IsGreaterThan"
                                           Value="55000"/>
			<telerik:NumericalFilterDescriptor PropertyName="StadiumCapacity"
                                               Operator="IsLessThan"
                                               Value="85000"/>
	</telerik:CompositeFilterDescriptor.Descriptors>
</telerik:CompositeFilterDescriptor>
```

### Delegate Filter Descriptor

The `DelegateFilterDescriptor` exposes the `Filter` property, which gets or sets the `IFilter` implementation used to check whether a data item passes the filter or not.

To use a `DelegateFilterDescriptor`, you need to create a class that implements the `IFilter` interface which will return the `Key` by which you want to filter.

Then, you need to add a `DelegateFilterDescriptor` to the `RadDataGrid.FilterDescriptors` collection and set its `Filter` property.

The following example demonstrates the `CustomFilter` implementation:

```C#
class CustomFilter : Telerik.Maui.Controls.Data.IFilter
{
    public bool PassesFilter(object item)
    {
        if(item is Club club 
           && club.StadiumCapacity > 60000 
           && club.StadiumCapacity < 85000)
        {
            return true;
        }
        else
        {
            return false;
        }
    }
}
```

> The `IFilter` interface is located in the `Telerik.Maui.Controls.Data` namespace.

Add the `DelegateFilterDescriptor` to the `RadDataGrid` instance:

```C#
treeDataGrid.FilterDescriptors.Add(new DelegateFilterDescriptor() { Filter = new CustomFilter()});
```

>important As the TreeDataGrid inherits from DataGrid, you can review the Programmatic Filtering scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **DataGrid > Filtering > Programmatic Filtering**.

## See Also

- [Filtering UI]({%slug treedatagrid-filtering-ui%})
- [Filter Control Template]({%slug treedatagrid-filter-control-template%})
- [Programmatic Filtering]({%slug treedatagrid-programmatic-filtering%})
