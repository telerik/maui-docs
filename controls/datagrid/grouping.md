---
title: Grouping
page_title: .NET MAUI DataGrid Documentation - Grouping
description: Check our &quot;Grouping&quot; documentation article for Telerik DataGrid for .NET MAUI control.
position: 4
slug: datagrid-grouping-overview
published: False
---

# Grouping

The DataGrid provides a programmatic approach for grouping its data based on specific criteria.

## Programmatic Grouping

Programmatic grouping can be done by adding descriptors to the `GroupDescriptors` collection. There are two types of descriptors:

* [PropertyGroupDescriptor](#property-group-descriptor)&mdash;Uses a property from the model as a group key.
* [DelegateGroupDescriptor](#delegate-group-descriptor)&mdash;Creates a custom group key which you can use.

All `GroupDescriptors` are located in the `Telerik.XamarinForms.Common.Data` namespace:

```XAML
 xmlns:telerikCommon="clr-namespace:Telerik.XamarinForms.Common.Data;assembly=Telerik.Maui.Controls.Compatibility"
```

### Property Group Descriptor

The `PropertyGroupDescriptor` is used to group the data in a DataGrid by property from the class that defines your objects.

To use the `PropertyGroupDescriptor`, you have to set its `PropertyName` (`string`) property, which gets or sets the name of the property that is used to retrieve the key by which to group.

>note You can sort the groups in ascending or descending order by using the `SortOrder` property.

Let's, for example, have the following business object:

<snippet id='datagrid-grouping-propertygroupdescriptor-object' />


Add a sample `ViewModel` class with a collection of `Person` objects:

<snippet id='datagrid-grouping-propertygroupdescriptor-viewmodel' />

Define the `DataGrid`:

<snippet id='datagrid-grouping-groupheadertemplate' />

All that is left is to set is the `ViewModel` as `BindingContext` of the page:

<snippet id='datagrid-grouping-propertygroupdescriptor-setvm' />

Apply the `PropertyGroupDescriptor`:

```C#
this.dataGrid.GroupDescriptors.Add(new Telerik.XamarinForms.Common.Data.PropertyGroupDescriptor()
{
    PropertyName="Department"
});
```

Here is how the DataGrid looks when it is grouped:

![DataGrid Property GroupDescriptor](images/datagrid_grouping.png)

### Delegate Group Descriptor

The difference between the `DelegateGroupDescriptor` and the `PropertyGroupDescriptor` is that the `DelegateGroupDescriptor` groups data by a custom key, while the `PropertyGroupDescriptor` groups by a defined key which is a property from the model.

You have to set the `KeyLookup` property of the `DelegateGroupDescriptor`, which gets or sets the `IKeyLookup` instance that is used to retrieve the group key for each data item.

>note You can sort the groups in ascending or descending order by using the `SortOrder` property.

You have to create a class that implements the `IKeyLookup` interface which will return the key by which you want to group. Then, you need to add the `DelegateGroupDescriptor` to the `RadDataGrid.GroupDescriptors` collection and set its `KeyLookup` property.

The following example demonstrates a sample `IKeyLookup` implementation:

<snippet id='datagrid-grouping-delegategroupdescriptor-lookup' />

Add it to the `GroupDescriptors` collection of the `RadDataGrid` instance:

<snippet id='datagrid-grouping-delegategroupdescriptor' />

Here is how the DataGrid looks when it is grouped through a `DelegateGroupDescriptor`:

![DataGrid Delegate GroupDescriptor](images/datagrid_grouping_delegategroup.png)

## Expand and Collapse Groups

The DataGrid supports group expand and collapse operations either through the UI by tapping on the group headers, or programmatically. By default, all the groups are expanded.

This section provides an overview of the methods and commands used to control the expand/collapse state of the DataGrid groups.

### Get the Grouped DataGrid Items

To manipulate the collapsible DataGrid groups, first you will need to call its `GetDataView` method. In short, the `GetDataView` method provides a view of the `ItemsSource` after all the sorting, grouping, and filtering operations are applied. The return type is `IDataViewCollection` which exposes the `expand` and `collapse` methods described in the following sections.

```C#
var dataView = this.dataGrid.GetDataView();
```

### Expand and Collapse All Groups

To expand all groups, use the `ExpandAll` method and, respectively, the `CollapseAll` method to collapse all groups.

```C#
//expand all
var dataView = this.dataGrid.GetDataView();
dataView.ExpandAll();

//collapse all
var dataView = this.dataGrid.GetDataView();
dataView.CollapseAll();
```

### Expand and Collapse Specific Groups

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

- [Columns]({%slug datagrid-columns-overview%})
- [Sorting]({%slug datagrid-sorting-overview%})
- [Filtering]({%slug datagrid-filtering-overview%})
- [Selection]({%slug datagrid-selection-overview%})
