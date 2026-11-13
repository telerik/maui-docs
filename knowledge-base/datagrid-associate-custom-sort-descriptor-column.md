---
title: Associate a Custom Sort Descriptor with a DataGrid Column
description: Learn how to keep the sort indicator of a custom .NET MAUI DataGrid column in sync when CreateSortDescriptor sorts by a different property.
type: how-to
page_title: Associate a Custom Sort Descriptor with a .NET MAUI DataGrid Column
meta_title: Associate a Custom Sort Descriptor with a .NET MAUI DataGrid Column
slug: datagrid-associate-custom-sort-descriptor-column
tags: datagrid, .net maui, sorting, sort descriptor, custom column, createsortdescriptor, isassociatedwithdescriptor, sort indicator
res_type: kb
---

## Environment

| Version | Product | Author |
| --- | --- | --- |
| 16.0.0 | Telerik UI for .NET MAUI DataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

A custom DataGrid column overrides the `CreateSortDescriptor` method and returns a `PropertySortDescriptor` that points to a property different from the `PropertyName` of the column. For example, a column displays a priority as text (`High`, `Medium`, `Low`) but sorts the rows by a numeric rank.

The DataGrid sorts the data correctly, but the column does not recognize the sort descriptor as its own. As a result, the column shows undesired visual effects, such as a stale sort indicator that remains visible after you sort by another column.

This knowledge base article also answers the following questions:

- How do I sort a DataGrid column by a property that is different from its `PropertyName`?
- Why does the sort indicator remain visible on a custom DataGrid column after I sort another column?
- How do I associate a custom sort descriptor with a DataGrid column in .NET MAUI?

## Cause

The DataGrid determines which column a descriptor belongs to by calling the `IsAssociatedWithDescriptor` method of each column. The default implementation of a typed column, such as `DataGridTextColumn`, compares the `PropertyName` of the descriptor with the `PropertyName` of the column.

When `CreateSortDescriptor` returns a descriptor with a different `PropertyName`, this comparison fails. The DataGrid then cannot update the sort state of the column when the descriptor is added, changed, or removed.

## Solution

To associate the custom sort descriptor with the column, override the `IsAssociatedWithDescriptor` method together with the `CreateSortDescriptor` method. The `IsAssociatedWithDescriptor` method is available for overriding starting with version 16.0.0.

The following example displays a `Priority` column that sorts the rows by the numeric `PriorityRank` property instead of alphabetically.

1. Create a custom column that inherits from `DataGridTextColumn`. Expose a `SortProperty` bindable property, return a `PropertySortDescriptor` for it from `CreateSortDescriptor`, and match the same property name in `IsAssociatedWithDescriptor`:

    ```C#
    using Microsoft.Maui.Controls;
    using Telerik.Maui.Controls.Data;
    using Telerik.Maui.Controls.DataGrid;

    public class CustomSortTextColumn : DataGridTextColumn
    {
        public static readonly BindableProperty SortPropertyProperty =
            BindableProperty.Create(nameof(SortProperty), typeof(string), typeof(CustomSortTextColumn));

        public string SortProperty
        {
            get => (string)this.GetValue(SortPropertyProperty);
            set => this.SetValue(SortPropertyProperty, value);
        }

        protected override bool IsAssociatedWithDescriptor(DataDescriptor descriptor)
        {
            if (descriptor is IPropertyDescriptor propertyDescriptor)
            {
                return propertyDescriptor.PropertyName == (this.SortProperty ?? this.PropertyName);
            }

            return false;
        }

        protected override SortDescriptorBase CreateSortDescriptor()
        {
            return new PropertySortDescriptor()
            {
                PropertyName = this.SortProperty ?? this.PropertyName
            };
        }
    }
    ```

2. Define the data model. The `Priority` property holds the displayed text, and the `PriorityRank` property holds the value used for sorting:

    ```C#
    public class TaskItem
    {
        public string Title { get; set; }

        public string Priority { get; set; }

        public int PriorityRank { get; set; }
    }
    ```

3. Define the `ViewModel`:

    ```C#
    using System.Collections.ObjectModel;

    public class TasksViewModel
    {
        public ObservableCollection<TaskItem> Tasks { get; } = new ObservableCollection<TaskItem>
        {
            new TaskItem { Title = "Update documentation", Priority = "Low", PriorityRank = 3 },
            new TaskItem { Title = "Fix login issue", Priority = "High", PriorityRank = 1 },
            new TaskItem { Title = "Review pull request", Priority = "Medium", PriorityRank = 2 },
            new TaskItem { Title = "Patch security issue", Priority = "High", PriorityRank = 1 },
        };
    }
    ```

4. Add the custom column to the `RadDataGrid` in Extensible Application Markup Language (XAML) and set its `SortProperty` to `PriorityRank`:

    ```XAML
    <telerik:RadDataGrid ItemsSource="{Binding Tasks}"
                         AutoGenerateColumns="False">
        <telerik:RadDataGrid.BindingContext>
            <local:TasksViewModel />
        </telerik:RadDataGrid.BindingContext>
        <telerik:RadDataGrid.Columns>
            <telerik:DataGridTextColumn PropertyName="Title"
                                        HeaderText="Task" />
            <local:CustomSortTextColumn PropertyName="Priority"
                                        HeaderText="Priority"
                                        SortProperty="PriorityRank" />
        </telerik:RadDataGrid.Columns>
    </telerik:RadDataGrid>
    ```

5. Add the `telerik` namespace and the `local` namespace, where `<YourAppNamespace>` is the namespace that contains the custom column, the data model, and the `ViewModel`:

    ```XAML
    xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
    xmlns:local="clr-namespace:<YourAppNamespace>"
    ```

When you tap the **Priority** column header, the DataGrid orders the rows as `High`, `Medium`, and `Low`, and the **Priority** column shows the sort indicator. When you tap the **Task** column header, the sort indicator moves to the **Task** column and the **Priority** column clears its indicator.

## Notes

- The `IsAssociatedWithDescriptor` override handles only `IPropertyDescriptor` instances.
- The `CreateSortDescriptor` and `IsAssociatedWithDescriptor` methods must resolve the same property name. If the two values differ, the column loses the association with its sort descriptor.
- For a `DataGridTemplateColumn`, set the `SortDescriptor` property instead. The template column associates itself with the descriptor assigned to that property.

## See Also

- [DataGrid Sorting]({%slug datagrid-sorting-overview%})
- [DataGrid Text Column]({%slug datagrid-columns-text-column%})
- [DataGrid Template Column]({%slug datagrid-columns-template-column%})
