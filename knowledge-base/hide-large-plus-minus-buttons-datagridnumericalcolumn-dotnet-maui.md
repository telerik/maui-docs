---
title: Hiding Large +- Button on DataGridNumericalColumn in UI for .NET MAUI
description: Learn how to hide or disable the large "+" and "-" buttons on the DataGridNumericalColumn in UI for .NET MAUI.
type: how-to
page_title: Removing Large +- Buttons from DataGridNumericalColumn in UI for .NET MAUI
meta_title: Removing Large +- Buttons from DataGridNumericalColumn in UI for .NET MAUI
slug: hide-large-plus-minus-buttons-datagridnumericalcolumn-dotnet-maui
tags: datagridnumericalcolumn, datagrid, numericinput, buttons, celleditorstyle
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 13.0.1 | Telerik UI for .NET MAUI DataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

The `DataGridNumericalColumn` in UI for .NET MAUI uses the [NumericInput](https://www.telerik.com/maui-ui/documentation/controls/numericinput/overview) control for editing. By default, this control displays large "+" and "-" buttons for increasing or decreasing the value. These buttons can obstruct the view on mobile devices and make it difficult to read the actual value. I need a way to hide or disable these buttons.

This knowledge base article also answers the following questions:
- How do I remove the large buttons from `DataGridNumericalColumn`?
- How can I disable the "+" and "-" buttons in the NumericInput editor?
- How do I customize the editing style in `DataGridNumericalColumn`?

## Solution

To hide the large "+" and "-" buttons, customize the `CellEditorStyle` of the `DataGridNumericalColumn`. Use a style targeting the `NumericInput` control to set the visibility of the buttons to `False`. Follow these steps:

1. Define a style for the `RadTemplatedButton` that sets its `IsVisible` property to `False`.
2. Define a style for the `RadNumericInput` that applies the button style to its `IncreaseButtonStyle` and `DecreaseButtonStyle` properties.
3. Apply the `CellEditorStyle` to the `DataGridNumericalColumn`.

The following XAML implements all three steps above:

```xml
<ContentPage.Resources>
    <Style x:Key="ButtonStyle" TargetType="telerik:RadTemplatedButton">
        <Setter Property="IsVisible" Value="False" />
    </Style>

    <Style x:Key="MyNumericColumnStyle" TargetType="telerik:RadNumericInput">
        <Setter Property="IncreaseButtonStyle" Value="{StaticResource ButtonStyle}" />
        <Setter Property="DecreaseButtonStyle" Value="{StaticResource ButtonStyle}" />
    </Style>
</ContentPage.Resources>

<telerik:RadDataGrid ItemsSource="{Binding GridItems}" AutoGenerateColumns="False">
    <telerik:RadDataGrid.Columns>
        <telerik:DataGridNumericalColumn CellEditorStyle="{StaticResource MyNumericColumnStyle}" PropertyName="Value" HeaderText="Value" />
    </telerik:RadDataGrid.Columns>
</telerik:RadDataGrid>
```

## See Also

- [Telerik UI for .NET MAUI NumericInput Documentation](https://www.telerik.com/maui-ui/documentation/controls/numericinput/overview)
- [Telerik UI for .NET MAUI DataGrid Overview](https://www.telerik.com/maui-ui/documentation/controls/datagrid/overview)
