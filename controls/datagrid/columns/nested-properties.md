---
title: Nested Properties
page_title: .NET MAUI DataGrid Documentation - Nested Properties Support
description: Check our &quot;Nested Properties&quot; documentation article for Telerik DataGrid for .NET MAUI.
position: 5
previous_url: /controls/datagrid/columns/datagrid-columns-nested-properties
slug: datagrid-nested-properties
---

# .NET MAUI DataGrid Nested Properties Support

The [Telerik UI for .NET MAUI DataGrid]({%slug datagrid-overview%}) provides support for nested properties - this allows binding of complex objects to the grid columns.

In addition, the DataGrid control provides the following property:  
* `ListenForNestedPropertyChange` (`bool`): Allows the DataGrid to listen for changes in the nested properties' values. The default value is `false`.

>tip `ListenForNestedPropertyChange` is `false` due to optimization purposes. You can enable it in case you'd need to update the nested properties' values.

## Example

Here is an example of how you can use the nested properties feature in DataGrid:

**1.** Create the needed business objects, for example type `Person` that will have property of type `Address`:

<snippet id='datagrid-nested-property-person' />

**2.** Create the Address model:

<snippet id='datagrid-nested-proprty-address' />

**3.** In the sample, both classes inherit from the `NotifyPropertyChangedBase` class, which implements the `INotifyPropertyChanged` interface. You would need to add the following namespace to use it:

```C#
using Telerik.Maui.Controls.Compatibility.Common;
```

**4.** Create a ViewModel with a collection of `Person` objects:

<snippet id='datagrid-nested-property-viewmodel' />

**5.** Use the following snippet to declare a `RadDataGrid` in XAML:

<snippet id='datagrid-nested-property-xaml' />

**6.** The `telerik` namespace is the following:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

Here is how the DataGrid looks:

![DataGrid Nested Properties](../images/datagrid-nested-properties.png)

## See Also

- [Picker Column]({%slug datagrid-columns-picker-column %})
- [Template Column]({%slug datagrid-columns-template-column %})
- [Text Column]({%slug datagrid-columns-text-column %})
