---
title: Enabling and Disabling Cell Editing in DataGrid for MAUI Based on Conditions
description: Learn how to control cell editing in the DataGrid for MAUI by applying conditions to specific cells or rows.
type: how-to
page_title: How to Conditionally Enable or Disable Cell Editing in DataGrid for MAUI
slug: datagrid-maui-conditional-cell-editing
tags: datagrid, maui, cell, edit, condition, enable, disable
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 10.0.0 | DataGrid for .NET MAUI | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

## Description

In scenarios where editing needs to be enabled or disabled for specific cells or rows in a DataGrid, the framework does not provide direct properties to accomplish this at the row level. This knowledge base article demonstrates how to selectively enable or disable cell editing in the [DataGrid for MAUI](https://docs.telerik.com/devtools/maui/controls/datagrid/commands/editing) by implementing a custom command. This solution is useful when the editability of a cell depends on certain conditions.


This knowledge base article also answers the following questions:
- How can I disable editing for specific cells in a DataGrid?
- Is it possible to control editing at the cell level in the DataGrid for MAUI?
- How do I implement conditional editing in the DataGrid based on the row data?

## Solution

To control the editability of specific cells or rows, create a custom `BeginEditCommand` and use a property in your data model to determine whether a cell should be editable. Follow these steps:

**1.** Define your `RadDataGrid` in XAML and set up the columns accordingly. Use the `UserEditMode` property to enable cell editing and define a custom command for initiating edits.

```xml
    <telerik:RadDataGrid x:Name="dataGrid" ItemsSource="{Binding Source}" AutoGenerateColumns="False" UserEditMode="Cell">
        <telerik:RadDataGrid.Columns>
            <telerik:DataGridTextColumn PropertyName="Name" SizeMode="Fixed" CanUserEdit="False"/>
            <telerik:DataGridNumericalColumn PropertyName="Value" CanUserEdit="False"/>
            <telerik:DataGridBooleanColumn PropertyName="IsEnabled" CanUserEdit="False"/>
            <telerik:DataGridDateColumn PropertyName="Date" CellContentFormat="{}{0:MM/dd/yyyy}" CanUserEdit="False"/>
            <telerik:DataGridTextColumn PropertyName="Text" />
        </telerik:RadDataGrid.Columns>
        <telerik:RadDataGrid.Commands>
            <local:BeginEditCommand />
        </telerik:RadDataGrid.Commands>
        ...
    </telerik:RadDataGrid>
```

**2.** Implement the data model class with an `IsEnabled` property to control the editability.

 ```csharp
    public class Data : NotifyPropertyChangedBase
    {
        private bool isEnabled;
        public string Value { get; set; }
        public bool IsEnabled
        {
            get { return this.isEnabled; }
            set { UpdateValue(ref this.isEnabled, value); }
        }

        public DateTime Date { get; set; }
        public string Text { get; set; }
    }
```

**3.** Create a ViewModel that includes a collection of data items.

 ```csharp
    public class ViewModel
    {
        public List<Data> Source { get; set; } = new List<Data>
        {
            new Data {Value ="One", IsEnabled=true, Date=new DateTime(2021,12,12), Text="Text 1"},
            new Data {Value ="Two", IsEnabled=false, Date=new DateTime(2021,12,13), Text="Text 2"},
            ...
        };
    }
```

**4.** Define the `BeginEditCommand` with custom logic to enable or disable editing based on the `IsEnabled` property.

```csharp
    public class BeginEditCommand : DataGridCommand
    {
        public BeginEditCommand()
        {
            this.Id = DataGridCommandId.BeginEdit;
        }
        public override bool CanExecute(object parameter)
        {
            return base.CanExecute(parameter);
        }
        public override void Execute(object parameter)
        {
            var context = (EditContext)parameter;
            var cellEdit = context.CellInfo as DataGridCellInfo;

            if (cellEdit != null && cellEdit.Column is DataGridTextColumn && cellEdit.Column.HeaderText == "Text" && (cellEdit.Item as Data).IsEnabled == true)
            {
                this.Owner.CommandService.ExecuteDefaultCommand(DataGridCommandId.BeginEdit, parameter);
            }
        }
    }
```

The provided solution allows for fine-grained control over cell editing in the DataGrid, enabling or disabling editing based on model properties or other conditions.

## See Also

- [DataGrid Commands Documentation](https://docs.telerik.com/devtools/maui/controls/datagrid/commands/overview)
- [Editing in DataGrid for MAUI](https://docs.telerik.com/devtools/maui/controls/datagrid/editing)
