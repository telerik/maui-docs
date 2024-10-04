---
title: Custom Sorting and Grouping in DataGrid Using Built-in UI in MAUI
description: Learn how to implement custom sorting and grouping logic in a Telerik DataGrid for MAUI while utilizing the built-in user interface options.
type: how-to
page_title: Customizing Sort and Group Logic in MAUI DataGrid with Built-in UI Features
slug: custom-sort-group-datagrid-maui
tags: datagrid, maui, custom, sort, group, delegate, descriptor
res_type: kb
---

## Environment

<table>
<tbody>
<tr>
<td>Product</td>
<td>DataGrid for MAUI</td>
</tr>
<tr>
<td>Version</td>
<td>7.1.0</td>
</tr>
</tbody>
</table>

## Description

When working with the Telerik [DataGrid](https://docs.telerik.com/devtools/maui/controls/datagrid/overview) for MAUI, you might need to customize the sorting and grouping logic while still allowing users to utilize the built-in UI options for these operations. This involves overriding the default sort and group descriptors with custom logic.

This KB article also answers the following questions:
- How can I implement custom sorting in a DataGrid while using the built-in UI in MAUI?
- Is it possible to use delegate descriptors for custom grouping in the DataGrid with the default UI?
- How do I enable users to sort and group DataGrid columns using custom logic in MAUI?

## Solution

To customize the sorting and grouping logic in a DataGrid while keeping the built-in UI functionality, follow these steps (the example uses the `DataGridComboBoxColumn` column):

1. Create a custom column class that inherits from `DataGridComboBoxColumn`.
2. Override the `CreateSortDescriptor()` and `CreateGroupDescriptor()` methods.
3. Implement your custom logic using `DelegateSortDescriptor` and `DelegateGroupDescriptor`.
4. Apply the custom column to the DataGrid control.

Below is a sample implementation:

```csharp
public class CustomComboBoxColumn : DataGridComboBoxColumn
{
    protected override GroupDescriptorBase CreateGroupDescriptor()
    {
        // Implement your custom grouping logic here
        return new DelegateGroupDescriptor() { DisplayContent = "", KeyLookup = new CustomIKeyLookup() };
    }

    protected override SortDescriptorBase CreateSortDescriptor()
    {
        // Implement your custom sorting logic here
        return new DelegateSortDescriptor() { KeyLookup = new CustomSortKeyLookup(), Comparer = new CustomComparer() };
    }
}
```

Then, define the custom columns within your DataGrid control in XAML:

```xml
<telerik:RadDataGrid ItemsSource="{Binding ItemsSource}"
                     AutoGenerateColumns="False" UserEditMode="Cell"
                     UserGroupMode="Enabled">
    <telerik:RadDataGrid.Columns>
        <local:CustomComboBoxColumn HeaderText="Column 4"
                                    PropertyName="Column4"
                                    ItemDisplayBindingPath="Name"
                                    ItemsSource="{Binding PlanTypes}">
        </local:CustomComboBoxColumn>

        <local:CustomComboBoxColumn HeaderText="Column 5"
                                    PropertyName="Column5"
                                    ItemDisplayBindingPath="Name"
                                    ItemsSource="{Binding TypeRecords}">
        </local:CustomComboBoxColumn>
    </telerik:RadDataGrid.Columns>
</telerik:RadDataGrid>
```

This approach allows you to maintain the user-friendly features of the DataGrid, like sorting and grouping through the UI, while applying your specific logic for these operations.

## See Also

- [DataGrid Overview](https://docs.telerik.com/devtools/maui/controls/datagrid/overview)
- [Grouping in DataGrid](https://docs.telerik.com/devtools/maui/controls/datagrid/grouping/delegate-group-descriptor)
- [Sorting in DataGrid](https://docs.telerik.com/devtools/maui/controls/datagrid/sorting#delegate-sort-descriptor)
