---
title: Editing Commands
page_title: .NET MAUI DataGrid Documentation | Editing Commands
description: Check our &quot;Editing Commands&quot; documentation article for Telerik DataGrid for .NET MAUI control.
position: 2
slug: datagrid-commands-editing
---

# Editing Commands

RadDataGrid control provides the following commands for editing the data inside the column:

* `BeginEdit`: Provides an entry point just before the editing begins.
* `CancelEdit`: Provides an entry point just before the editing is canceled.
* `CommitEdit`: Provides an entry point just before the editing is committed.

The execution parameter of the `Editing Commands` is of type *EditContext* that exposes the following properties:

* `CellInfo`: Gets the cell info associated with the operation.
* `TriggerAction`: Gets the SourceTriggerAction value that triggered the operation.
* `Parameter`: Gets an optional parameter holding additional information associated with the operation.

## BeginEdit and CommitEdit Commands Example

Here is an example how the RadDataGrid Editing Commands work.

First, create the needed business objects, for example type Data with the following properties:

<snippet id='datagrid-commands-editing-businessobject'/>
```C#
public class Data
{
    public string Country { get; set; }
    public string Capital { get; set; }
}
```

Then create a ViewModel with a collection of Data objects:

<snippet id='datagrid-commands-editing-viewmodel'/>
```C#
public class ViewModel
{    
    public ViewModel()
    {
        this.Items = new ObservableCollection<Data>()
        {
            new Data { Country = "India", Capital = "New Delhi"},
            new Data { Country = "South Africa", Capital = "Cape Town"},
            new Data { Country = "Nigeria", Capital = "Abuja" },
            new Data { Country = "Singapore", Capital = "Singapore" }
        };
    }

	public ObservableCollection<Data> Items { get; set; }
}
```

Set the ViewModel class as BindingContext of the page:

```C#
this.BindingContext = new ViewModel();
```

Then handle the BeginEdit action as a Command. First, create a class that inherits from the `DataGridCommand` and set its Id property accordingly.
You would also need to override CanExecute and Execute methods as demonstrated in the example below:

<snippet id='datagrid-commands-editing-beginedit'/>
```C#
public class BeginEditCommand : DataGridCommand
{
    public BeginEditCommand()
    {
        this.Id = DataGridCommandId.BeginEdit;
    }

    public override void Execute(object parameter)
    {
        var context = (EditContext)parameter;
        var cellEdit = $"BeginEdit on: {context.CellInfo.Value} via {context.TriggerAction} \n";
        Application.Current.MainPage.DisplayAlert("", "" + cellEdit, "OK");
        this.Owner.CommandService.ExecuteDefaultCommand(DataGridCommandId.BeginEdit, parameter);
    }
}
```

Then handle the CommitEdit action as a Command. First, create a class that inherits from the `DataGridCommand` and set its Id property accordingly.
You would also need to override CanExecute and Execute methods as demonstrated in the example below:

<snippet id='datagrid-commands-editing-commitedit'/>
```C#
public class CommitEditCommand : DataGridCommand
{
    public CommitEditCommand()
    {
        this.Id = DataGridCommandId.CommitEdit;
    }

    public override void Execute(object parameter)
    {
        var context = (EditContext)parameter;

        Application.Current.MainPage.DisplayAlert("", "Edit Committed", "OK");
        this.Owner.CommandService.ExecuteDefaultCommand(DataGridCommandId.CommitEdit, parameter);
    }
}
```

Then add this Commands to the Commands collection of the RadDataGrid instance:

<snippet id='datagrid-commands-editing-binding'/>
```C#
dataGrid.Commands.Add(new BeginEditCommand());
dataGrid.Commands.Add(new CommitEditCommand());
```

Define the RadDataGrid in XAML:

<snippet id='datagrid-commands-editing'/>
```XAML
<telerikDataGrid:RadDataGrid x:Name="dataGrid"
                             ItemsSource="{Binding Items}"
                             UserEditMode="Cell"/>
```

## See Also

- [Validation]({%slug datagrid-commands-validation%})
- [DataGrid Styling]({%slug datagrid-styling%})
- [Columns Styling]({%slug datagrid-columns-styling%})
