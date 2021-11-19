---
title: CellTap Command
page_title: .NET MAUI DataGrid Documentation | CellTap Command
description: Check our &quot;CellTap Command&quot; documentation article for Telerik DataGrid for .NET MAUI control.
position: 1
slug: datagrid-commands-cell-tap
---

# CellTap Command

The DataGrid `CellTap` command handles the tap (click) gesture over a grid cell, that is, the intersection of a data row and a column.

## Example

Here is an example how the RadDataGrid `CellTap` command works:

First, create the needed business objects, for example, type `Country` with the following properties:

<snippet id='datagrid-commands-celltap-businessobject'/>
```C#
public class Data
{
    public string Country { get; set; }
    public string Capital { get; set; }
}
```

Then, create a `ViewModel` with a collection of `Data` objects:

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

Set the `ViewModel` class as `BindingContext` of the page:

```C#
this.BindingContext = new ViewModel();
```

Then, handle the `CellTap` action as a command. First, create a class that inherits from the `DataGridCommand` and set its `Id` property accordingly. You will also need to override the `CanExecute` and `Execute` methods as demonstrated in the example below:

<snippet id='datagrid-commands-celltap'/>
```C#
public class CellTapUserCommand: DataGridCommand
{
	public CellTapUserCommand()
	{
		Id = DataGridCommandId.CellTap;
	}
	public override bool CanExecute(object parameter)
	{
		return true;
	}
	public override void Execute(object parameter)
	{
		var context = parameter as DataGridCellInfo;
		var cellTap = $"CellTap Command on cell {context.Value} inside {context.Column.HeaderText} \n";
		Application.Current.MainPage.DisplayAlert("", "You've selected " + cellTap, "OK");
		this.Owner.CommandService.ExecuteDefaultCommand(DataGridCommandId.CellTap, parameter);
	}
}
```

Then, add this command to the `Commands` collection of the `RadDataGrid` instance:

<snippet id='datagrid-commands-cetttap-add'/>
```C#
dataGrid.Commands.Add(new CellTapUserCommand());
```

Define the DataGrid in XAML:

<snippet id='datagrid-commands-celltap-xaml'/>
```XAML
<telerikDataGrid:RadDataGrid x:Name="dataGrid"
							 ItemsSource="{Binding Items}"/>
```

## See Also

- [Editing]({%slug datagrid-commands-editing%})
- [Validation]({%slug datagrid-commands-validation%})
