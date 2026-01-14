---
title: Managing SelectedItems in TreeDataGrid
description: Learn how to manage the read-only SelectedItems collection in Telerik UI for .NET MAUI TreeDataGrid by binding it to a ViewModel property.
type: how-to
page_title: How to Bind and Manage SelectedItems in TreeDataGrid
meta_title: Bind and Manage SelectedItems in Telerik MAUI TreeDataGrid
slug: managing-selecteditems-treedatagrid
tags: treedatagrid, ui for .net maui, selecteditems, binding, collectionchanged
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | ---- | ---- | 
| 12.1.0 | Telerik UI for .NET MAUI TreeDataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to manage the `SelectedItems` property in the Telerik [TreeDataGrid](https://docs.telerik.com/devtools/maui/controls/treedatagrid/overview) for .NET MAUI. The `SelectedItems` collection is read-only, inaccessible in XAML, and cannot use two-way binding. This is by design and applies to similar collections in Telerik MAUI controls like AutoComplete `Tokens`, ComboBox `SelectedItems`, DataGrid `SelectedItems`, and CollectionView `SelectedItems`.

This knowledge base article also answers the following questions:
- How to bind the `SelectedItems` property in TreeDataGrid?
- How to manage the `SelectedItems` collection in Telerik MAUI controls?
- How to handle `CollectionChanged` events?

## Solution

To manage the `SelectedItems` collection, bind it to a property in the ViewModel and handle property changes using the `CollectionChanged` event.

**1.** Define the ViewModel with an `ObservableCollection` for `SelectedItems`. Subscribe to the `CollectionChanged` event.

```csharp
public class ViewModel : NotifyPropertyChangedBase
{
    private ObservableCollection<object> selectedItems;
    public ObservableCollection<Data> Items { get; set; }

    public ObservableCollection<object> SelectedItems
    {
        get => this.selectedItems;
        set
        {
            if (this.selectedItems != value)
            {
                if (this.selectedItems != null)
                {
                    this.selectedItems.CollectionChanged -= SelectedItems_CollectionChanged;
                }

                this.selectedItems = value;

                if (this.selectedItems != null)
                {
                    this.selectedItems.CollectionChanged += SelectedItems_CollectionChanged;
                }

                OnPropertyChanged();
            }
        }
    }

    private void SelectedItems_CollectionChanged(object sender, System.Collections.Specialized.NotifyCollectionChangedEventArgs e)
    {
        if (e.Action == NotifyCollectionChangedAction.Add)
        {
            // Handle added items
        }
        else if (e.Action == NotifyCollectionChangedAction.Remove)
        {
            // Handle removed items
        }
    }
}
```

**2.** Bind the `TreeDataGrid`'s `SelectedItems` and `ItemsSource` properties to the ViewModel.

```xaml
<telerik:RadTreeDataGrid x:Name="treeDataGrid"
                         SelectionMode="Multiple"
                         SelectedItems="{Binding SelectedItems}"
                         ItemsSource="{Binding Items}"/>
```

## See Also

- [TreeDataGrid Overview](https://www.telerik.com/maui-ui/documentation/controls/treedatagrid/overview)
- [Selection in TreeDataGrid for .NET MAUI](https://www.telerik.com/maui-ui/documentation/controls/treedatagrid/selection)
