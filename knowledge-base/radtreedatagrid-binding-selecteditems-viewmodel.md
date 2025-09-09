---
title: Binding SelectedItems Collection TreeDataGrid to ViewModel
description: Explains why SelectedItems in RadTreeDataGrid cannot be bound directly in XAML and shows how to use it in the ViewModel.
type: how-to
page_title: Using SelectedItems in RadTreeDataGrid with ViewModel Binding
meta_title: Using SelectedItems in RadTreeDataGrid with ViewModel Binding
slug: radtreedatagrid-binding-selecteditems-viewmodel
tags: radtreedatagrid, .net maui, selecteditems, binding, xaml, viewmodel
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.1.0 | Telerik UI for .NET MAUI TreeDataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I need to bind the `SelectedItems` property of [TreeDataGrid](https://docs.telerik.com/devtools/maui/controls/treedatagrid/overview) to a collection property in my `ViewModel`, but I noticed that it is not available for binding in XAML. However, it seems accessible in the code-behind file. Is there a way to bind this collection to the `ViewModel`?

This knowledge base article also answers the following questions:

- Why is `SelectedItems` not available for binding in XAML?
- How can I work with `SelectedItems` in the `ViewModel`?
- How can I use `SelectedItems` with collection updates?

## Solution

The `SelectedItems` property of the TreeDataGrid is a read-only collection with a private setter, which means it cannot be directly bound in XAML. IntelliSense does not suggest properties with private setters for XAML binding, and therefore, two-way binding is not supported.

To use `SelectedItems` in your `ViewModel`, follow these steps:

**1.** Define the TreeDataGrid control:

```XAML
<telerik:RadTreeDataGrid x:Name="treeDataGrid" ItemsSource="{Binding Items}"
							SelectedItems="{Binding Selection, Mode=OneWayToSource}"
							SelectionMode="Multiple"
							AutoGenerateColumns="False">
	<telerik:RadTreeDataGrid.ItemDescriptor>
		<telerik:TreeDataGridItemDescriptor ItemsSourceBinding="{Binding Children}" />
	</telerik:RadTreeDataGrid.ItemDescriptor>
	<telerik:RadTreeDataGrid.Columns>
		<telerik:DataGridTextColumn PropertyName="Name" />
		<telerik:DataGridNumericalColumn PropertyName="Size" />
		<telerik:DataGridTextColumn PropertyName="Type" />
	</telerik:RadTreeDataGrid.Columns>
</telerik:RadTreeDataGrid>
```

**2.** Define the `ViewModel` and subscribe to the `CollectionChanged` event of the `SelectedItems` property. This event notifies you when the selection changes.

```C#
public class MainPageViewModel : NotifyPropertyChangedBase
{
	private ObservableCollection<object> selection;

	public MainPageViewModel()
    {
		Items = new ObservableCollection<Data>();
		Items.Add(new Data("My Projects", 234, "Folder")
		{
			Children = new ObservableCollection<Data>()
				{
					new Data("Using latest Telerik .NET MAUI controls", 234 ,"Folder")
					{
						Children = new ObservableCollection<Data>()
						{
							new Data("TreeDataGrid", 6, "File"),
							new Data("CollectionView", 6, "File"),
							new Data("DataGrid", 54, "File"),
							new Data("Scheduler", 12, "File"),
							new Data("TreeView", 2, "File"),
							new Data("Calendar", 23, "File"),
							new Data("RichTextEditor", 0, "File"),
							new Data("PdfViewer", 55, "File"),
							new Data("ToggleButton", 21, "File"),
							new Data("TemplatedButton", 88, "File"),
						}
					},
					new Data("Blank project", 0, "Folder")
				}
		});
		Items.Add(new Data("Shared Documents", 643, "Folder")
		{
			Children = new ObservableCollection<Data>()
				{
					new Data("Reports", 643, "Folder")
					{
						Children = new ObservableCollection<Data>()
						{
							new Data("October", 234, "File"),
							new Data("November", 0, "File"),
							new Data("December", 409, "File")
						}
					}
				}
		});
		Items.Add(new Data("Pictures", 643, "Folder")
		{
			Children = new ObservableCollection<Data>()
				{
					new Data("Camera Roll", 231, "Folder")
					{
						Children = new ObservableCollection<Data>()
						{
							new Data("hello.png", 107, "File"),
							new Data("happy_summer.png", 0, "File"),
							new Data("avatar.png", 124, "File")
						}
					},
					new Data("Saved Pictures", 453, "Folder")
					{
						Children = new ObservableCollection<Data>()
						{
							new Data("vacation.png", 234, "File"),
							new Data("november.png", 0, "File"),
							new Data("mountains.png", 227, "File")
						}
					}
				}
		});
		Items.Add(new Data("Documents", 876, "Folder")
		{
			Children = new ObservableCollection<Data>()
				{
					new Data("Internal Usage Only", 643, "Folder")
					{
						Children = new ObservableCollection<Data>()
						{
							new Data("reports.docx", 234, "File"),
							new Data("confidential.xlsx", 0, "File"),
							new Data("internal_usage.pdf", 409, "File")
						}
					}
				}
		});
	}
	public ObservableCollection<Data> Items { get; set; }

	public ObservableCollection<object> Selection
	{
		get => this.selection;
		set
		{
			if (this.selection != value)
			{
				if (this.selection != null)
				{
					this.selection.CollectionChanged -= SelectedItems_CollectionChanged;
				}

				this.selection = value;
                Device.StartTimer(TimeSpan.FromMicroseconds(300), () =>
                {
					this.selection.Add(this.Items[0]);
                    return false;
				});
				
				this.OnPropertyChanged();

				if (this.selection != null)
				{
					this.selection.CollectionChanged += SelectedItems_CollectionChanged;
				}
			}
		}
	}

	private void SelectedItems_CollectionChanged(object? sender, System.Collections.Specialized.NotifyCollectionChangedEventArgs e)
	{
		if (e.Action == NotifyCollectionChangedAction.Add)
		{
			// add your logic here
		}
		else if (e.Action == NotifyCollectionChangedAction.Remove)
		{
			// add your logic here
		}
	}
}
```

**3.** Define the data model:

```C#
public class Data
{
	public Data(string name, int size, string type)
	{
		this.Name = name;
		this.Size = size;
		this.Type = type;
		this.Children = new ObservableCollection<Data>();
	}

	public string Name { get; set; }
	public int Size { get; set; }
	public string Type { get; set; }
	public ObservableCollection<Data> Children { get; set; }
}
```

**4.** Set the binding context:

```XAML
    <ContentPage.BindingContext>
        <viewmodels:MainPageViewModel />
    </ContentPage.BindingContext>
```

## See Also

- [TreeDataGrid Overview](https://docs.telerik.com/devtools/maui/controls/treedatagrid/overview)
