---
title: Sorting and Grouping in Descending Order in RadDataGrid
description: Learn how to sort and group items in the RadDataGrid for UI for .NET MAUI in descending order.
type: how-to
page_title: Setting Sort and Group Descriptors to Descending Order in RadDataGrid
meta_title: Setting Sort and Group Descriptors to Descending Order in RadDataGrid
slug: datagrid-sorting-grouping-descending-order
tags: datagrid, ui-for-dotnet-maui, sort-descriptors, group-descriptors, descending-order
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.1.0 | DataGrid for .NET MAUI | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

When the user groups the DataGrid through the UI, I need the groups to appear in descending order. Currently, the items are sorted by `FirstContactDate` in descending order, but when grouped, the grouping defaults to ascending order. The goal is to allow users to see the latest entries grouped by `FirstContactDate` in descending order.

This knowledge base article also answers the following questions:
- How to sort and group items in descending order in DataGrid?
- How to set group descriptors to descending order in Telerik DataGrid for .NET MAUI?
- How to change the group descriptor order dynamically during grouping?

## Solution

To achieve sorting and grouping in descending order, follow one of the approaches below.

### Option 1: Set Sort and Group Descriptors Explicitly

Define both `SortDescriptors` and `GroupDescriptors` with the desired `SortOrder` in the XAML configuration.

```xaml
<telerik:RadDataGrid.GroupDescriptors>
    <telerik:PropertyGroupDescriptor PropertyName="FirstContactDate" SortOrder="Descending" />
</telerik:RadDataGrid.GroupDescriptors>

<telerik:RadDataGrid.SortDescriptors>
    <telerik:PropertySortDescriptor PropertyName="FirstContactDate" SortOrder="Descending" />
</telerik:RadDataGrid.SortDescriptors>
```

### Option 2: Change Group Sort Order at Runtime

Use the `GroupDescriptors.CollectionChanged` event to dynamically update the `SortOrder` of the group descriptor when a column is grouped. For example:

```csharp
public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();
        BindingContext = new RegistrationViewModel();

        this.dataGrid.GroupDescriptors.CollectionChanged += GroupDescriptors_CollectionChanged;
    }

    private void GroupDescriptors_CollectionChanged(object? sender, System.Collections.Specialized.NotifyCollectionChangedEventArgs e)
    {
        if (e.Action != NotifyCollectionChangedAction.Add)
            return;
        
        var groupDescriptor = e.NewItems[0] as GroupDescriptorBase;
        if (groupDescriptor != null)
        {
            groupDescriptor.SortOrder = SortOrder.Descending;
        }
    }
}
```

## See Also

- [DataGrid Documentation](https://docs.telerik.com/devtools/maui/controls/datagrid/overview)
