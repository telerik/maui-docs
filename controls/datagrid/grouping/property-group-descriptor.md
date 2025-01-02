---
title: Property Group Descriptor
page_title: .NET MAUI DataGrid Documentation - Property Group Descriptor
description: "Review the Telerik .NET MAUI DataGrid Property Group Descriptor documentation article to learn more about the property grouping function you can use."
position: 2
slug: datagrid-property-group-descriptor
---

# Property Group Descriptor for .NET MAUI DataGrid

The `PropertyGroupDescriptor` is used to group the data in a [.NET MAUI DataGrid]({%slug datagrid-overview%}) by property from the class that defines your objects.

To use the `PropertyGroupDescriptor`, you have to set its `PropertyName` (`string`) property, which gets or sets the name of the property that is used to retrieve the key by which to group.

To specify the content that is used to represent the group descriptor visually within the grouping panel, you have to set the `DisplayContent` (`object`) property.

>note You can sort the groups in ascending or descending order by using the `SortOrder` property.

Let's, for example, have the following business object:

<snippet id='datagrid-grouping-object' />

Add a sample `ViewModel` class with a collection of `Person` objects:

<snippet id='datagrid-grouping-viewmodel' />

Define the `DataGrid`:

<snippet id='datagrid-grouping-propertygroupdescriptor-xaml' />

All that is left is to set is the `ViewModel` as `BindingContext` of the page:

<snippet id='datagrid-grouping-propertygroupdescriptor-setvm' />

Apply the `PropertyGroupDescriptor`:

<snippet id='datagrid-grouping-propertygroupdescriptor' />

Here is how the DataGrid looks when it's grouped:

![DataGrid Property GroupDescriptor](../images/datagrid-property-group-descriptor.png)

## See Also

- [Grouping UI]({%slug datagrid-grouping-ui%})
- [Group Header Template]({%slug datagrid-group-header-template%})