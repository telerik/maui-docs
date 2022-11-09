---
title: Column Reordering
page_title: .NET MAUI DataGrid Documentation - Column Reordering
description: Check our &quot;Reordering&quot; documentation article for Telerik DataGrid for .NET MAUI control.
position: 7
slug: datagrid-columns-reordering
---

# .NET MAUI DataGrid Column Reordering

The DataGrid exposes a reordering feature allowing the user to drag and drop columns and change their order.

![DataGrid Reordering Desktop](../images/datagrid-reordering-mac.gif)

## Properties

`CanUserReorderColumns`(`bool`)&mdash;Defines whether the user can reorder the `DataGridColumns`. The default value is `True`.
`ColumnReorderIndicatorTemplate`(`DataTemplate`)&mdash;Defines the template that presents the indicator which is shown between two columns during reordering.

## Example

### CanUserReorderColumns

The following example shows how to bind the `CanUserReorderColumns` using MVVM.

Define the DataGrid and a control which will change the `CanUserReorderColumns` value in XAML:

<snippet id='datagrid-reordering-example'/>

Define the ViewModel:

<snippet id='datagrid-reordering-viewmodel'/>

The result on mobile:

![DataGrid Reordering Phone](../images/datagrid-reordering-android.gif)

### ColumnReorderIndicatorTemplate

The following example shows how to define the `ColumnReorderIndicatorTemplate` in XAML:

Define the DataTemplate for the Indicator in the Resources of the page:
```XAML
<ContentView.Resources>
    <DataTemplate x:Key="reorderingIndicator">
        <Label Text="Place here" TextColor="Red"/>
    </DataTemplate>
</ContentView.Resources>
```

Define the property in the DataGrid:
```XAML
<telerik:RadDataGrid x:Name="dataGrid"
                     Grid.Row="1"
                     CanUserReorderColumns="{Binding IsReorderingEnabled}"
                     ItemsSource="{Binding Data}"/>   
```

The result on mobile:

![DataGrid Reordering Phone](../images/datagrid-reordering-indicator.png)

## See Also

- [Picker Column]({%slug datagrid-columns-picker-column %})
- [Template Column]({%slug datagrid-columns-template-column %})
- [Text Column]({%slug datagrid-columns-text-column %})