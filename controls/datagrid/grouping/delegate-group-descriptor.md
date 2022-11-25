---
title: Delegate Group Descriptor
page_title: .NET MAUI DataGrid Documentation - Delegate Group Descriptor
description: "Review the Telerik .NET MAUI DataGrid Delegate Group Descriptor  documentation article to learn more about the delegate grouping function you can use."
position: 3
slug: datagrid-delegate-group-descriptor
---

# Delegate Group Descriptor for .NET MAUI DataGrid

The difference between the `DelegateGroupDescriptor` and the [PropertyGroupDescriptor]({%slug datagrid-property-group-descriptor%}) is that the `DelegateGroupDescriptor` groups data by a custom key, while the `PropertyGroupDescriptor` groups by a defined key which is a property from the model.

You have to set the `KeyLookup` property of the `DelegateGroupDescriptor`, which gets or sets the `IKeyLookup` instance that is used to retrieve the group key for each data item.

>note You can sort the groups in ascending or descending order by using the `SortOrder` property.

You have to create a class that implements the `IKeyLookup` interface which will return the key by which you want to group. Then, you need to add the `DelegateGroupDescriptor` to the `RadDataGrid.GroupDescriptors` collection and set its `KeyLookup` property.

The following example demonstrates a sample `IKeyLookup` implementation:

<snippet id='datagrid-grouping-delegategroupdescriptor-lookup' />

Add it to the `GroupDescriptors` collection of the `RadDataGrid` instance:

<snippet id='datagrid-grouping-delegategroupdescriptor' />

Here is how the DataGrid looks when it is grouped through a `DelegateGroupDescriptor`:

![DataGrid Delegate GroupDescriptor](../images/datagrid_grouping_delegategroup.png)