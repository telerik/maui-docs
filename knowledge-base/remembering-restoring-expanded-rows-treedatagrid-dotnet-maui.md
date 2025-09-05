---
title: Remembering and Restoring Expanded Rows in TreeDataGrid for .NET MAUI
description: Learn how to efficiently remember expanded rows and restore them in TreeDataGrid for .NET MAUI.
type: how-to
page_title: Efficiently Remember and Restore Expanded Rows in TreeDataGrid for .NET MAUI
meta_title: Efficiently Remember and Restore Expanded Rows in TreeDataGrid for .NET MAUI
slug: remembering-restoring-expanded-rows-treedatagrid-dotnet-maui
tags: treedatagrid, .net maui, expand, collapse, isexpanded, isexpandablebinding
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.1.0 | Telerik UI for .NET MAUI TreeDataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to remember the expanded rows in the TreeDataGrid and restore them later. What is the most efficient way to achieve this?

This knowledge base article also answers the following questions:
- How can I store expanded items in TreeDataGrid for later use?
- How can I restore the expansion state in TreeDataGrid after changes?
- What is the best way to manage expanded rows in TreeDataGrid?

## Solution

To achieve the scenario you can use one of the following approaches:
* [Using `Expand` and `Collapse` Methods](#using-expand-and-collapse-methods)
* [Using `IsExpandableBinding` property of the `TreeDataGridDescriptor`](#using-isexpandablebinding)

### Using Expand and Collapse Methods

To achieve this, follow these steps:

1. Use `Expand()` and `Collapse()` methods to expand or collapse items.
2. Use the `IsExpanded` method to check whether an item is expanded.
3. Store the expanded items in a collection, such as a `List<YourDataClass>`.
4. Iterate through the collection to restore the expanded state by calling the `Expand()` method.

```C#
public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();
        this.BindingContext = new ViewModel();
    }

    // Collection for storing expanded items
    List<Data> expandedItems = new List<Data>();

    private void Button_Clicked(object sender, EventArgs e)
    {
        var items = (IEnumerable)this.tdg.ItemsSource;
        this.expandedItems = new List<Data>();
        AddExpandedItems(items, expandedItems);
    }

    private void AddExpandedItems(IEnumerable items, List<Data> expandedItems)
    {
        foreach (Data item in items)
        {
            if (this.tdg.IsExpanded(item))
            {
                expandedItems.Add(item);
            }

            IEnumerable childrenOfTheItem = item.Children;
            AddExpandedItems(childrenOfTheItem, expandedItems);
        }
    }

    private void Button2_Clicked(object sender, EventArgs e)
    {
        foreach (Data item in this.expandedItems)
        {
            this.tdg.Expand(item);
        }
    }
}
```

### Using `IsExpandableBinding`

As an alternative, use the [`IsExpandableBinding`](https://docs.telerik.com/devtools/maui/controls/treedatagrid/descriptor) property at the descriptor level:

1. Add a `bool` property in the data model to indicate whether an item is expandable.
2. Bind this property to the `IsExpandableBinding` property of the TreeDataGrid descriptor.
3. Implement the logic in button clicks to get and restore expanded items.

This approach provides direct control over the expandability of rows via data binding.

## See Also

- [TreeDataGrid Overview](https://docs.telerik.com/devtools/maui/controls/treedatagrid/overview)
- [Expand and Collapse Methods in TreeDataGrid](https://docs.telerik.com/devtools/maui/controls/treedatagrid/methods)
