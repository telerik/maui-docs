---
title: Nested Properties
page_title: .NET MAUI DataGrid Documentation - Nested Properties Support
description: Check our &quot;Nested Properties&quot; documentation article for Telerik DataGrid for .NET MAUI.
position: 5
previous_url: /controls/datagrid/columns/datagrid-columns-nested-properties
slug: datagrid-nested-properties
---

# Nested Properties Support

DataGrid provides support for nested properties - this allows binding of complex objects to the grid columns.

In addition, the DataGrid control provides the following property:  
* `ListenForNestedPropertyChange` *(bool)*: Allows the DataGrid to listen for changes of the nested properties' values. By default it is *false*.

>tip ListenForNestedPropertyChange is false due to optimization purposes, you could enable it in case you'd need to update the nested properties' values.

## Example

Here is an example how you could utilize the nested properties feature in DataGrid:

1. Create the needed business objects, for example type `Person` that will have property of type `Address`:

 <snippet id='datagrid-nested-property-person' />

1. Create Address model

 <snippet id='datagrid-nested-proprty-address' />

In the sample both classes inherit from NotifyPropertyChangedBase class which basically implements the INotifyPropertyChanged interface. You would need to add the following namespace to use it:

 ```C#
using Telerik.XamarinForms.Common;
 ```

1. Create a ViewModel with a collection of `Person` objects:

 <snippet id='datagrid-nested-property-viewmodel' />

1. Use the following snippet to declare a RadDataGrid in XAML:

 <snippet id='datagrid-nested-property-xaml' />

1. The `telerik` namespace is the following:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

Here is how tha DataGrid looks:

![DataGrid Nested Properties](../images/datagrid-nested-properties.png)

## See Also

- [Picker Column]({%slug datagrid-columns-picker-column %})
- [Template Column]({%slug datagrid-columns-template-column %})
- [Text Column]({%slug datagrid-columns-text-column %})
