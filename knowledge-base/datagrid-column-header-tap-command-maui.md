---
title: Executing a Custom Command on DataGrid Column Header Tap in UI for .NET MAUI
description: Learn how to use the ColumnHeaderTap command in the DataGrid component of UI for .NET MAUI to execute custom logic when a column header is clicked.
type: how-to
page_title: Implementing Custom Functionality for DataGrid Column Header Tap in UI for .NET MAUI
meta_title: Implementing Custom Functionality for DataGrid Column Header Tap in UI for .NET MAUI
slug: datagrid-column-header-tap-command-maui
tags: datagrid, ui for .net maui, columnheader, command
res_type: kb
---

## Environment

| Version | Product | Author |
| --- | --- | ---- |
| 13.0.0 | Telerik UI for .NET MAUI DataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)|

## Description

I need to execute a custom command when a column header in the DataGrid is clicked. Is there a tapped command or similar functionality to bind custom logic to the header's click event?

This knowledge base article also answers the following questions:

- How to override the default sorting behavior of DataGrid headers?
- How to bind custom logic to DataGrid column header tap in UI for .NET MAUI?
- How to add a custom command to the DataGrid component?

## Solution

To execute custom logic when a DataGrid column header is clicked, use the `ColumnHeaderTap` command. By default, this command sorts the column, but you can override the behavior.

1. Define the DataGrid with columns in XAML:

```xaml
<telerik:RadDataGrid ItemsSource="{Binding Items}" x:Name="grid" AutoGenerateColumns="False">
    <telerik:RadDataGrid.Columns>
        <telerik:DataGridTextColumn HeaderText="Name" PropertyName="Name" />
        <telerik:DataGridNumericalColumn HeaderText="Age" PropertyName="Age" />
        <telerik:DataGridTextColumn HeaderText="Email" PropertyName="Email" />
    </telerik:RadDataGrid.Columns>
    <telerik:RaddataGrid.BindingContext>
        <local:MainViewModel />
    </telerik:RaddataGrid.BindingContext>
</telerik:RadDataGrid>
```

2. Create a `ViewModel` with sample data:

```csharp
public class MainViewModel
{
    public ObservableCollection<Person> Items { get; } = new()
    {
        new Person { Name = "Alice", Age = 30, Email = "" },
        new Person { Name = "Bob", Age = 25, Email = "" },
        new Person { Name = "Charlie", Age = 35, Email = "" }
    };
}

public class Person
{
    public string Name { get; set; } = string.Empty;
    public int Age { get; set; }
    public string Email { get; set; } = string.Empty;
}
```

3. Implement a custom `ColumnHeaderTapCommand` by inheriting from the `DataGridCommand` class.

```csharp
public class ColumnHeaderTapCommand : DataGridCommand
{
    public ColumnHeaderTapCommand()
    {
        Id = DataGridCommandId.ColumnHeaderTap;
    }

    public override bool CanExecute(object parameter)
    {
        return true;
    }

    public override void Execute(object parameter)
    {
        if (parameter is Telerik.Maui.Controls.DataGrid.DataGridTextColumn)
        {
            // Add your custom logic here
        }
    }
}
```

4. Add the custom command to the DataGrid's `Commands` collection.

```csharp
this.grid.Commands.Add(new ColumnHeaderTapCommand());
```

## See Also

- [DataGrid Documentation for UI for .NET MAUI](https://www.telerik.com/maui-ui/documentation/controls/datagrid/overview)
- [DataGrid Commands Documentation](https://www.telerik.com/maui-ui/documentation/controls/datagrid/commands/overview)
