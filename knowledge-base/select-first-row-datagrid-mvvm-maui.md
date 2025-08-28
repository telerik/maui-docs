---
title: Selecting the First Row in DataGrid by Default Using MVVM in UI for .NET MAUI
description: Learn how to select the first row in a UI for .NET MAUI DataGrid by default using the MVVM approach.
type: how-to
page_title: Automatically Select the First Row in UI for .NET MAUI DataGrid Using MVVM
meta_title: Automatically Select the First Row in UI for .NET MAUI DataGrid Using MVVM
slug: select-first-row-datagrid-mvvm-maui
tags: datagrid, ui-for-net-maui, mvvm, default-selection, selecteditem
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.1.0 | DataGrid for .NET MAUI | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to select the first row in the [DataGrid](https://docs.telerik.com/devtools/maui/controls/datagrid/overview) component by default using an MVVM approach.

This knowledge base article also answers the following questions:
- How to set a default selected row in the UI for .NET MAUI DataGrid?
- How to bind the DataGrid's `SelectedItem` property in MVVM?
- How to programmatically select the first row in a DataGrid?

## Solution

To select the first row by default, bind the `SelectedItem` property of the DataGrid to a property in the `ViewModel` and set its value to the first item in the collection.

1. Define the `ViewModel`: Create a `SelectedItem` property in the `ViewModel` to hold the selected row.

```csharp
private MyItem selectedItem;

public ObservableCollection<MyItem> Items { get; set; }

public MyItem SelectedItem
{
    get => this.selectedItem;
    set
    {
        if (this.selectedItem != value)
        {
            this.selectedItem = value;
            OnPropertyChanged(nameof(this.SelectedItem));
        }
    }
}

public event PropertyChangedEventHandler PropertyChanged;
protected virtual void OnPropertyChanged(string propertyName) =>
    this.PropertyChanged?.Invoke(this, new PropertyChangedEventArgs(propertyName));
```

This setup ensures that changes to the `SelectedItem` property automatically notify the UI to refresh.

2. Set the Default Selection: Assign the first item in the collection to the `SelectedItem` property.

```csharp
public MainViewModel()
{
    this.Items = new ObservableCollection<MyItem>
    {
        new MyItem { Name = "Item 1", Description = "First item description" },
        new MyItem { Name = "Item 2", Description = "Second item description" },
        new MyItem { Name = "Item 3", Description = "Third item description" }
    };

    this.SelectedItem = this.Items[0]; // Select the first item.
}
```

3. Bind the ViewModel to the DataGrid: In XAML, bind the `SelectedItem` property of the DataGrid to the `ViewModel` and set the binding mode to `TwoWay`.

```xml
<telerik:RadDataGrid 
    ItemsSource="{Binding Items}" 
    SelectedItem="{Binding SelectedItem, Mode=TwoWay}" />
```

This approach ensures that the first row in the DataGrid is selected by default.

## See Also

- [DataGrid Overview](https://docs.telerik.com/devtools/maui/controls/datagrid/overview)
- [MVVM Pattern in .NET MAUI](https://learn.microsoft.com/en-us/dotnet/maui/xaml/fundamentals/mvvm)
- [ObservableCollection Class](https://learn.microsoft.com/en-us/dotnet/api/system.collections.objectmodel.observablecollection-1) 
