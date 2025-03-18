---
title: Displaying Collection of Items in .NET MAUI DataGrid ComboBox Column
description: Learn how to populate the ComboBox column in Telerik MAUI DataGrid with a collection and configure the display settings.
type: how-to
page_title: How to Use ComboBox Column in Telerik MAUI DataGrid
slug: datagrid-combobox-column-maui
tags: datagrid, combobox, collection, maui, display, itemssource, propertyname, itemdisplaybindingpath
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 10.0.0 | Telerik UI for .NET MAUI ComboBox, DataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

How can I use the ComboBox column in the DataGrid to display a collection of items? Additionally, how should I configure the `PropertyName` and `ItemDisplayBindingPath` for the column?

This knowledge base article also answers the following questions:
- How to bind a collection to a ComboBox column in a DataGrid?
- What are `PropertyName` and `ItemDisplayBindingPath` in a DataGrid ComboBox column?
- How to display item names from a collection in a DataGrid ComboBox column?

## Solution

To use the ComboBox column in the Telerik MAUI DataGrid to display a collection of items, follow these steps:

**1.** Define  the collection.

Create an `ObservableCollection` of the type that will be displayed in the ComboBox. For example, if displaying categories, create an `ObservableCollection<Category>`.

```csharp
public ObservableCollection<Category> AllCategories { get; set; }


this.AllCategories = new ObservableCollection<Category>
{
	new(){ Id = 0, Name = "Boston"},
	new(){ Id = 1, Name = "San Francisco"},
	new(){ Id = 2, Name = "Tokyo"},
	new(){ Id = 3, Name = "London"}
};
```

**2.** Define the `DataModel`
Ensure the model used in the DataGrid has a property that corresponds to the ComboBox. For example, an `Employee` class with a `Person` property.

```csharp
public class Employee : NotifyPropertyChangedBase
{
	private string name;
	private Category person;

	public Employee()
	{
	}

	public string Name
	{
		get => name;
		set => UpdateValue(ref name, value);
	}

	public Category Person
	{
		get => person;
		set => UpdateValue(ref person, value);
	}
}
```

**3.**Create the `Category` class.
 Define a class for the items to be displayed in the ComboBox. Include properties such as `Id` and `Name` for display and identification.

```csharp
public class Category
{
    public string Id { get; set; }
    public string Name { get; set; }
}
```

**4.** Configure the DataGridComboBoxColumn.
In your XAML, define the `DataGridComboBoxColumn` with the `HeaderText`, `PropertyName`, `ItemDisplayBindingPath`, and `ItemsSource`. The `PropertyName` should be the property of the data model. The `ItemDisplayBindingPath` specifies which property of the ComboBox items will be displayed.

```xml
<telerik:DataGridComboBoxColumn HeaderText="Person"
                                PropertyName="Person"
                                ItemDisplayBindingPath="Name"
                                ItemsSource="{Binding AllCategories, Mode=TwoWay}" />
```

By following these steps, the `DataGridComboBoxColumn` will display the `Name` property of the `Category` object associated with each person, using the `AllCategories` collection as the source of items for the ComboBox.

## See Also

- [ComboBox Overview]({%slug combobox-overview%})
