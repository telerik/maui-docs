---
title: Binding SortDescriptors in CollectionView for .NET MAUI
description: Learn how to use data binding with CollectionView SortDescriptors in .NET MAUI applications.
type: how-to
page_title: How to Bind SortDescriptors in .NET MAUI CollectionView
slug: bind-sortdescriptors-collectionview-net-maui
tags: collectionview, sortdescriptors, databinding, .net maui, observablecollection
res_type: kb
ticketid: 1677846
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 9.0.0 | Telerik UI for .NET MAUI CollectionView | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

In my application, I want to use data binding to bind to an `ObservableCollection` of sort descriptors.

This knowledge base article also answers the following questions:
- How to dynamically sort items in a CollectionView using `SortDescriptors` in .NET MAUI?
- How to bind SortDescriptors to a ViewModel property in .NET MAUI?
- How to update CollectionView sorting based on user input in .NET MAUI?

## Solution

To bind the `SortDescriptors` collection in a `CollectionView` to a property in the ViewModel, follow these steps:

1. Define the CollectionView in XAML and bind the `SortDescriptors` and `ItemsSource` to the `ViewModel` properties.

```xml
<Grid RowDefinitions="auto,*">
    <VerticalStackLayout>
        <Switch IsToggled="{Binding IsSortByName}" />
        <Switch IsToggled="{Binding IsSortByAge}" />
    </VerticalStackLayout>
    <telerik:RadCollectionView x:Name="listView"
                             Grid.Row="1"
                             SortDescriptors="{Binding SortDescriptors, Mode=OneWayToSource}"
                             ItemsSource="{Binding Items}">
        <telerik:RadCollectionView.ItemTemplate>
            <DataTemplate>
                <HorizontalStackLayout Spacing="10" >
                    <Label Text="{Binding Name}"/>
                    <Label Text="{Binding Age}"/>
                </HorizontalStackLayout>
            </DataTemplate>
        </telerik:RadCollectionView.ItemTemplate>
    </telerik:RadCollectionView>
</Grid>
```

2. In the `ViewModel`, create properties for sorting and managing data. Implement logic to update the sort descriptors based on the user input.

```csharp
public class ViewModel : NotifyPropertyChangedBase
{
	private bool isSortByName;
	private bool isSortByAge;

	private ObservableCollection<SortDescriptorBase> sortDescriptors;

	public ViewModel()
	{
		this.Items = GetData();
	}

	private static ObservableCollection<Person> GetData()
	{
		var items = new ObservableCollection<Person>();

		items.Add(new Person { Name = "Tom", Age = 41 });
		items.Add(new Person { Name = "Anna", Age = 32 });
		items.Add(new Person { Name = "Peter", Age = 28 });
		items.Add(new Person { Name = "Teodor", Age = 39 });
		items.Add(new Person { Name = "Lorenzo", Age = 25 });
		items.Add(new Person { Name = "Andrea", Age = 33 });
		items.Add(new Person { Name = "Martin", Age = 36 });
		items.Add(new Person { Name = "Alexander", Age = 29 });
		items.Add(new Person { Name = "Maria", Age = 22 });
		items.Add(new Person { Name = "Elena", Age = 27 });
		items.Add(new Person { Name = "Stefano", Age = 44 });
		items.Add(new Person { Name = "Jake", Age = 31 });
		items.Add(new Person { Name = "Leon", Age = 28 });

		return items;
	}
	public bool IsSortByName
	{
		get => this.isSortByName;
		set => this.UpdateValue(ref this.isSortByName, value);
	}

	public bool IsSortByAge
	{
		get => this.isSortByAge;
		set => this.UpdateValue(ref this.isSortByAge, value);
	}

	public ObservableCollection<Person> Items { get; set; }

	public ObservableCollection<SortDescriptorBase> SortDescriptors
	{
		get
		{
			return this.sortDescriptors;
		}
		set
		{
			ObservableCollection<SortDescriptorBase> oldValue = this.sortDescriptors;

			if (this.UpdateValue(ref this.sortDescriptors, value))
			{
				this.OnSortDescriptorsChanged(oldValue);
			}
		}
	}


	protected override void OnPropertyChanged([CallerMemberName] string propertyName = null)
	{
		base.OnPropertyChanged(propertyName);

		this.UpdateCorrespondingDescriptor(propertyName);
	}

	private void OnSortDescriptorsChanged(ObservableCollection<SortDescriptorBase> oldValue)
	{
		if (oldValue != null)
		{
			oldValue.CollectionChanged -= this.SortDescriptors_CollectionChanged;
		}

		if (this.sortDescriptors != null)
		{
			this.sortDescriptors.CollectionChanged += SortDescriptors_CollectionChanged;
		}

		this.UpdateFlags();
	}

	private void SortDescriptors_CollectionChanged(object? sender, System.Collections.Specialized.NotifyCollectionChangedEventArgs e)
	{
		this.UpdateFlags();
	}

	private void UpdateCorrespondingDescriptor(string propertyName)
	{
		if (propertyName == nameof(this.IsSortByName))
		{
			this.EnsureDescriptor(nameof(Person.Name), this.IsSortByName);
		}
		else if (propertyName == nameof(this.IsSortByAge))
		{
			this.EnsureDescriptor(nameof(Person.Age), this.IsSortByAge);
		}
	}

	private void EnsureDescriptor(string propertyName, bool include)
	{
		ObservableCollection<SortDescriptorBase> descriptors = this.SortDescriptors;

		if (descriptors == null)
		{
			return;
		}

		SortDescriptorBase descriptor = this.TryGetDescriptor(propertyName);

		if (include)
		{
			if (descriptor == null)
			{
				descriptors.Add(new PropertySortDescriptor { PropertyName = propertyName });
			}
		}
		else
		{
			if (descriptor != null)
			{
				descriptors.Remove(descriptor);
			}
		}
	}

	private void UpdateFlags()
	{
		this.IsSortByName = this.TryGetDescriptor(nameof(Person.Name)) != null;
		this.IsSortByAge = this.TryGetDescriptor(nameof(Person.Age)) != null;
	}

	private SortDescriptorBase TryGetDescriptor(string propertyName)
	{
		SortDescriptorBase descriptor = this.sortDescriptors?.FirstOrDefault(d => (d as PropertySortDescriptor)?.PropertyName == propertyName);
		return descriptor;
	}
}
public class Person
{
	public string Name { get; set; }
	public int Age { get; set; }
}

```

3. Ensure that property change notifications are properly propagated, and the `SortDescriptors` collection is updated accordingly when switches are toggled.

This approach allows for dynamic sorting of items in the `CollectionView` based on user input, by binding `SortDescriptors` to a collection managed in the ViewModel.

## See Also

- [CollectionView Overview in .NET MAUI]({%slug collectionview-overview%})
- [Data Binding in .NET MAUI](https://learn.microsoft.com/en-us/dotnet/maui/xaml/fundamentals/mvvm?view=net-maui-9.0)
- [Implementing Model-View-ViewModel (MVVM) in .NET MAUI](https://learn.microsoft.com/en-us/dotnet/architecture/maui/mvvm)
