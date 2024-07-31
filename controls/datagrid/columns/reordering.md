---
title: Columns Reordering
page_title: .NET MAUI DataGrid Documentation - Column Reordering
description: Check our &quot;Reordering&quot; documentation article for Telerik DataGrid for .NET MAUI control.
position: 7
slug: datagrid-columns-reordering
---

# .NET MAUI DataGrid Columns Reordering

The [.NET MAUI DataGrid]({%slug datagrid-overview%}) exposes a reordering feature allowing the user to drag and drop columns and change their order.

![DataGrid Reordering Desktop](../images/datagrid-reordering-mac.gif)

`CanUserReorderColumns`(`bool`)&mdash;Defines whether the user can reorder the `DataGridColumns`. The default value is `True`.
`ColumnReorderIndicatorTemplate`(`DataTemplate`)&mdash;Defines the template that presents the indicator which is shown between two columns during reordering.

## Events

The DataGrid exposes the follwoing events related to reordering operation:

* `ColumnReorderStarting`&mdash;Raised when the user starts to drag a column to reorder it. The `ColumnReorderStarting` event handler receives the following parameters:
    - `sender` argument which is of type `object`, but can be cast to the `RadDataGrid` type.
    - `ColumnReorderStartingEventArgs` which has a reference to the following properties:
        - `Column` (`DataGridColumn`)&mdash;Gets the colum that will be reordered.
        - `Index` (`int`) &mdash;Gets the index of the column that will be reordered.
        - `Cancel` (`bool`)&mdash;Defines a value indicating whether the reordering operation is canceled.

* `ColumnReordering`&mdash;Raised continuously while the column is being dragged. The `ColumnReordering` event handler receives the following parameters:
    - `sender` argument which is of type `object`, but can be cast to the `RadDataGrid` type.
    - `ColumnReorderingEventArgs` which has a reference to the following properties:
        - `Column` (`DataGridColumn`)&mdash;Gets the colum that will be reordered.
        - `OldIndex` (`int`) &mdash;Gets the initial index of the column that is being reordered.
        - `NewIndex` (`int`) &mdash;Gets the new potential index of the column that is being reordered.
        - `NewIsFrozen` (`bool`)&mdash;Gets the new potential `Telerik.Maui.Controls.DataGrid.DataGridColumn.IsFrozen` value of the column that is being reordered.
        - `CanDrop` (`bool`)&mdash;Defines a value indicating whether dropping the column at this specific location is allowed. The default value is `true`.

* `ColumnReorderCompleting`&mdash;Raised when the user drops the column. This doesn't mean the column is reordered. The `ColumnReorderCompleting` event handler receives the following parameters:
    - `sender` argument which is of type `object`, but can be cast to the `RadDataGrid` type.
    - `ColumnReorderCompletingEventArgs` which has a reference to the following properties:
        - `Column` (`DataGridColumn`)&mdash;Gets the column that is being reordered.
        - `OldIndex` (`int`) &mdash;Gets the initial index of the column that is being reordered.
        - `NewIndex` (`int`) &mdash;Gets the new potential index of the column that is being reordered.
        - `NewIsFrozen` (`bool`)&mdash;Gets the new potential `Telerik.Maui.Controls.DataGrid.DataGridColumn.IsFrozen` value of the column that is being reordered.
        - `IsDropAllowed` (`bool`)&mdash;Gets a value that indicates whether the column was dropped at a valid location. A valid location means that the column has changed its index and/or the value of its `IsFrozen` property and the drop at this location was not forbidden by setting the `Telerik.Maui.Controls.DataGrid.ColumnReorderingEventArgs.CanDrop` property of the `Telerik.Maui.Controls.DataGrid.ColumnReorderingEventArgs` to `false`. The default value is `true`.
        - `Cancel` (`bool`)&mdash;Defines a value indicating whether the reordering operation is canceled.

* `ColumnReordered`&mdash;Raised when a column has been successfully reordered. The `ColumnReordered` event handler receives the following parameters:
    - `sender` argument which is of type `object`, but can be cast to the `RadDataGrid` type.
    - `ColumnReorderCompletingEventArgs` which has a reference to the following properties:
        - `Column` (`DataGridColumn`)&mdash;Gets the colum that has been reordered.
        - `OldIndex` (`int`) &mdash;Gets the initial index of the column that has been reordered.
        - `OldIsFrozen` (`bool`)&mdash;Gets the initial `Telerik.Maui.Controls.DataGrid.DataGridColumn.IsFrozen` value of the column that has been reordered.
        - `NewIndex` (`int`) &mdash;Gets the new index of the column that has been reordered.

## Example with Reorder Columns and Events

The following example shows how to bind the `CanUserReorderColumns` using MVVM and a sample scenario with the reordering events.

**1.** Create a sample model:

<snippet id='datagrid-persondetails' />

**2.** Create a `ViewModel`:

<snippet id='datagrid-reordering-viewmodel' />

**3.** Define the DataGrid and a control which will change the `CanUserReorderColumns` value in XAML:

<snippet id='datagrid-reordering-example'/>

**4.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**5.** Sample implementation in the reordering event:

<snippet id='datagrid-column-reordering-events'/>

The result on mobile:

![DataGrid Reordering Phone](../images/datagrid-reordering-winui.gif)

## Example with Indicator Template when Reordering Columns

The following example shows how to define the `ColumnReorderIndicatorTemplate` in XAML:

**1.** Define the `DataTemplate` for the Indicator in the Resources of the page:

```XAML
<DataTemplate x:Key="reorderingIndicator">
    <telerik:RadBorder BackgroundColor="LightSalmon"
                       WidthRequest="4"
                       HeightRequest="55"
                       HorizontalOptions="Start"
                       VerticalOptions="Start"
                       InputTransparent="True" />
</DataTemplate>
```

**2.** Define the property in the DataGrid:

```XAML
<telerik:RadDataGrid x:Name="dataGrid"
                     Grid.Row="1"
                     ColumnReorderIndicatorTemplate="{StaticResource reorderingIndicator}"
                     ItemsSource="{Binding Data}"/>    
```

The result on mobile:

![DataGrid Reordering Indicator Phone](../images/datagrid-reordering-indicator.gif)

## See Also

- [Picker Column]({%slug datagrid-columns-picker-column %})
- [Template Column]({%slug datagrid-columns-template-column %})
- [Text Column]({%slug datagrid-columns-text-column %})