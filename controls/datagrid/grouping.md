---
title: Grouping
page_title: .NET MAUI DataGrid Documentation | Grouping Overview
description: Check our &quot;Grouping&quot; documentation article for Telerik DataGrid for .NET MAUI control.
position: 4
slug: datagrid-grouping-overview
---

# Grouping

**RadDataGrid** provides programmatic approach for grouping its data per concrete criteria. 

## Programmatic Grouping

Programmatic grouping can be done by adding descriptors to the **GroupDescriptors** collection. There are two types of descriptors:

* [**PropertyGroupDescriptor**](#property-group-descriptor): use a property from the model as a group key.
* [**DelegateGroupDescriptor**](#delegate-group-descriptor): create a custom group key which you can use.

All GroupDescriptors are located in the Telerik.XamarinForms.Common.Data namespace:

```XAML
 xmlns:telerikCommon="clr-namespace:Telerik.XamarinForms.Common.Data;assembly=Telerik.Maui.Controls.Compatibility"
```

### Property Group Descriptor

The PropertyGroupDescriptor is used to group the data in a DataGrid by property from the class that defines your objects.

To use the PropertyGroupDescriptor you have to set its property PropertyName.

* **PropertyName** (string): Gets or sets the name of the property that is used to retrieve the key to group by.

>note You can easily sort the groups in ascending or descending order using the **SortOrder** property.

Let's, for example, have the following business object:

```C#
public class Person
{
    public string Name { get; set; }
    public int Age { get; set; }
    public string Department { get; set; }
}
```

And a ViewModel class with a collection of **Person** objects:

```C#
public class ViewModel
{
    public ViewModel()
    {
        this.People = new ObservableCollection<Person>()
        {
            new Person { Name = "Kiko", Age = 23, Department = "Production" },
            new Person { Name = "Jerry", Age = 23, Department = "Accounting and Finance"},
            new Person { Name = "Ethan", Age = 51, Department = "Marketing" },
            new Person { Name = "Isabella", Age = 25, Department = "Marketing" },
            new Person { Name = "Joshua", Age = 45, Department = "Production" },
            new Person { Name = "Logan", Age = 26, Department = "Production"},
            new Person { Name = "Aaron", Age = 32, Department = "Production" },
            new Person { Name = "Elena", Age = 37, Department = "Accounting and Finance"},
            new Person { Name = "Ross", Age = 30, Department = "Marketing" },
        };
    }

    public ObservableCollection<Person> People { get; set; }
}
```

Next snippet demonstrates how you could group the people by "Department" property through the PropertyGroupDescriptor:

```XAML
<telerikDataGrid:RadDataGrid x:Name="dataGrid"
							 ItemsSource="{Binding People}">
	<telerikDataGrid:RadDataGrid.GroupDescriptors>
		<telerikCommon:PropertyGroupDescriptor PropertyName="Department" />
	</telerikDataGrid:RadDataGrid.GroupDescriptors>
</telerikDataGrid:RadDataGrid>
```

All that is left is to set the ViewModel as BindingContext of the page:

```C#
this.BindingContext = new ViewModel();
```

Here is how the RadDataGrid looks when it is grouped:

![](images/datagrid_grouping.png)

### Delegate Group Descriptor

The difference between the **DelegateGroupDescriptor** and the **PropertyGroupDescriptor** is that DelegateGroupDescriptor groups data by a custom Key while the PropertyGroupDescriptor groups by a defined Key which is a property from our model.

You have to set the following property of the DelegateGroupDescriptor:

 * **KeyLookup**: Gets or sets the **IKeyLookup** instance that is used to retrieve the group key for each data item.

>note You can easily sort the groups in ascending or descending order using the **SortOrder** property.

You have to create a class that implements the **IKeyLookup** interface which will return the Key you want to group by. Then you need to add the **DelegateGroupDescriptor** to the RadDataGrid.GroupDescriptors collection and set its **KeyLookup** property.

Check below a sample **IKeyLookup** implementation:

```C#
class CustomIKeyLookup : Telerik.XamarinForms.Common.Data.IKeyLookup
{
    public object GetKey(object instance)
    {
        var item = instance as Person;
        return item?.Name[0];
    }
}
```

Adding it to the **GroupDescriptors** collection of the **RadDataGrid**:

```C#
this.dataGrid.GroupDescriptors.Add(new DelegateGroupDescriptor() { KeyLookup = new CustomIKeyLookup() });
```

Here is how the RadDataGrid looks when it is grouped through a DelegateGroupDescriptor:

![](images/datagrid_grouping_delegategroup.png)

## Expand and Collapse Groups

**RadDataGrid** supports groups expand and collapse operations either through the UI by tapping on the group headers or programmatically. By default, all the groups are expanded.

This help topic will provide an overview of the methods and commands used to control the expand/collapse state of the DataGrid groups.

### Get the grouped DataGrid items

To manipulate the collapsible DataGrid groups, first you will need to call its **GetDataView** method. In short, GetDataView method provides a view of the ItemsSource after all the Sort, Group and Filter operations are applied.  The return type is *IDataViewCollection* which exposes the expand and collapse methods described in the following sections.

```C#
var dataView = this.dataGrid.GetDataView();
```

### Expand and collapse all groups 

In order to expand all groups, use the **ExpandAll** method and respectively use the **CollapseAll** method - to collapse all groups.

```C#
//expand all
var dataView = this.dataGrid.GetDataView();
dataView.ExpandAll();

//collapse all
var dataView = this.dataGrid.GetDataView();
dataView.CollapseAll();
```

### Expand and collapse a certain group

You could retrieve the first-level groups through the **GetGroups** method of the *IDataViewCollection* object and use **ExpandGroup**/**CollapseGroup** to make a certain group to expand or collapse respectively. You could check whether a group is expanded trough the **GetIsExpanded** method.

Here is quick snippet on how these methods are used:

```C# 
var dataView = this.dataGrid.GetDataView();
var rootGroups = dataView.GetGroups();

var isFirstExpanded = dataView.GetIsExpanded(rootGroups.First());
//expand a certain group
dataView.ExpandGroup(rootGroups.First());
//collapse a certain group
dataView.CollapseGroup(rootGroups.First());
```

Additionally, *IDataViewCollection* provides **ExpandItem**/**CollapseItem** methods that takes a data item as a parameter and expand/collapse the immediate group containing this item.	

```C#
var lastItem = (dataGrid.ItemsSource as IEnumerable<City>).Last();
var dataView = this.dataGrid.GetDataView();
dataView.CollapseItem(lastItem);
```

## See Also

- [Columns]({%slug datagrid-columns-overview%})
- [Sorting]({%slug datagrid-sorting-overview%})
- [Selection]({%slug datagrid-selection-overview%})
