---
title: Filtering
page_title: .NET MAUI DataGrid Documentation | Filtering
description: Check our &quot;Filtering&quot; documentation article for Telerik DataGrid for .NET MAUI control.
position: 5
slug: datagrid-filtering-overview
---

# Filtering

The DataGrid provides programmatic approach for filtering its data per concrete criteria.

## Programmatic Filtering

Programmatic filtering is achieved by adding different filter descriptors in the `FilterDescriptor` collection of the control. The following descriptor types are supported:

* [`TextFilterDescriptor`](#text-filter-descriptor)
* [`NumericalFilterDescriptor`](#numerical-filter-descriptor)
* [`DateTimeFilterDescriptor`](#datetime-filter-descriptor)
* [`BooleanFilterDescriptor`](#boolean-filter-descriptor)
* [`CompositeFilterDescriptor`](#composite-filter-descriptor)
* [`DelegateFilterDescriptor`](#delegate-filter-descriptor)

All FilterDescriptors are located in the Telerik.XamarinForms.Common.Data namespace:

```XAML
xmlns:telerikCommon="clr-namespace:Telerik.XamarinForms.Common.Data;assembly=Telerik.Maui.Controls.Compatibility"
```

### Text Filter Descriptor

Properties:

* `PropertyName`: Gets or sets the name of the property that is used to retrieve the value to filter by.
* `Operator`: Gets or sets the TextOperator value that defines how the Value member is compared with each value from the items source.
* `Value`: Gets or sets the value used in the comparisons. This is the right operand of the comparison.
* `IsCaseSensitive`: Gets or sets a value that determines whether the text comparisons will be case-sensitive. Default value is true.

To use `TextFilterDescriptor` you need to add its instance to the `RadDataGrid.FilterDescriptors` collection and to set its `PropertyName` property to associate it with the property from your custom objects. Then through the `Operator` and `Value` properties you need to set the filter condition and the value to compare. You can also take advantage of the `IsCaseSensitive` property to determine if the text comparisons will be case-sensitive or not.

<snippet id='datagrid-textfilterdescriptor-xaml'/>
```XAML
<telerikCommon:TextFilterDescriptor PropertyName="Country"
                             Operator="StartsWith"
                             IsCaseSensitive="False"
                             Value="En"/>
```

### Numerical Filter Descriptor

Represents a Descriptor which filters by property of numerical data type. It exposes the following properties.

* `PropertyName`: Gets or sets the name of the property that is used to retrieve the value to filter by.
* `Value`: Gets or sets the value used in the comparisons. This is the right operand of the comparison.
* `Operator`: Gets or sets the NumericalOperator value that defines the boolean logc behind the left and right operand comparison.

<snippet id='datagrid-numericalfilterdecsriptor-xaml'/>
```XAML
<telerikCommon:NumericalFilterDescriptor PropertyName="StadiumCapacity"
                                  Operator="IsLessThan"
                                  Value="80000"/>
```

### DateTime Filter Descriptor

The DateTimeFilterDescriptor is a Descriptor which filters by property of System.DateTime data type. It exposes the following properties:

* `PropertyName`: Gets or sets the name of the property that is used to retrieve the value to filter by.
* `Value`: Gets or sets the value used in the comparisons. This is the right operand of the comparison.
* `Operator`: Gets or sets the NumericalOperator value that defines the boolean logic behind the left and right operand comparison.

<snippet id='datagrid-datetimefilterdescriptor-xaml'/>
```XAML
<telerikCommon:DateTimeFilterDescriptor PropertyName="Established"
                                 Operator="IsLessThan"
                                 Value="1900/01/01"/>
```

### Boolean Filter Descriptor

The BooleanFilterDescriptor is a Descriptor which filters by property of System.Boolean data type. It exposes the following properties:

* `PropertyName`: Gets or sets the name of the property that is used to retrieve the value to filter by.
* `Value`: Gets or sets the value used in the comparisons. This is the right operand of the comparison.

<snippet id='datagrid-booleanfilterdescriptor-xaml'/>
```XAML
<telerikCommon:BooleanFilterDescriptor PropertyName="IsChampion"
                                Value="true"/>
```

### Composite Filter Descriptor

The CompositeFilterDescriptor represents a special FilterDescriptorBase that stores an arbitrary number of other Descriptors instances. The logical AND or OR operator is applied upon all composed filters to determine the result of the PassesFilter routine.

<snippet id='datagrid-compositefilterdescriptor-xaml'/>
```XAML
<telerikCommon:CompositeFilterDescriptor Operator="And">
	<telerikCommon:CompositeFilterDescriptor.Descriptors>
		<telerikCommon:NumericalFilterDescriptor PropertyName="StadiumCapacity"
                                          Operator="IsGreaterThan"
                                          Value="55000"/>
			<telerikCommon:NumericalFilterDescriptor PropertyName="StadiumCapacity"
                                              Operator="IsLessThan"
                                              Value="85000"/>
	</telerikCommon:CompositeFilterDescriptor.Descriptors>
</telerikCommon:CompositeFilterDescriptor>
```

### Delegate Filter Descriptor

The DelegateFilterDescriptor exposes the following property:

* `Filter`: Gets or sets the `IFilter` implementation used to check whether a data item passes the filter or not.

To use a `DelegateFilterDescriptor` you need to create a class that implements the `IFilter` interface which will return the `Key` you want to filter by.

Then you need to add a DelegateFilterDescriptor to the RadDataGrid.FilterDescriptors collection and set its Filter property.

The `CustomFilter` implementation:

<snippet id='datagrid-delegatefilterdescriptor-csharp'/>
```C#
class CustomFilter : IFilter
{
	public bool PassesFilter(object item)
 	{
		if ((item as Club).StadiumCapacity > 60000 && (item as Club).StadiumCapacity <85000)
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

Adding the `DelegateFilterDescriptor` to the `RadDataGrid`:

<snippet id='datagrid-delegatefilterdescriptor-added'/>
```C#
dataGrid.FilterDescriptors.Add(new DelegateFilterDescriptor() { Filter = new CustomFilter()});
```

## See Also

- [Grouping]({%slug datagrid-grouping-overview%})
- [Sorting]({%slug datagrid-sorting-overview%})
- [Selection]({%slug datagrid-selection-overview%})
