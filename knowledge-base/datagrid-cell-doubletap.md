---
title: Execute CellTap command on CellDoubleTap in DataGrid
description: Execute the CellTap command in CellDoubleTap command in the RadDataGrid for .NET MAUI.
type: how-to
page_title: Execute the CellTap command in CellDoubleTap command in DataGrid
slug: datagrid-cell-doubletap
position: 
tags: 
ticketid: 1611664
res_type: kb
---

## Environment
<table>
    <tbody>
        <tr>
            <td>Product Version</td>
            <td>5.2.0</td>
        </tr>
        <tr>
            <td>Product</td>
            <td>DataGrid for MAUI</td>
        </tr>
    </tbody>
</table>


## Description

This how-to article describes how to execute the `CellTap` command in `CellDoubleTap` command in the RadDataGrid for .NET MAUI.

## Solution

Here is an example how to execute the `CellTap` command in `CellDoubleTap` command.

1. Create the needed business objects, for example, the `Country` type with the following properties:

```C#
public class Country
{
public Country(string name, double population)
{
    this.Name = name;
    this.Population = population;
}

public string Name { get; set; }
public double Population { get; set; }
}
```

2. Add data to the DataGrid `ItemsSource` and set the Binding Context:

```C#
var source = new ObservableCollection<Country>();
source.Add(new Country("Mozambique", 24692000));
source.Add(new Country("Paraguay", 6725000));
source.Add(new Country("Turkmenistan", 5663000));
source.Add(new Country("Mongolia", 3027000));
source.Add(new Country("Japan", 127000000));
source.Add(new Country("Bulgaria", 7128000));
source.Add(new Country("Chad", 14450000));
source.Add(new Country("Netherlands", 17020000));


this.BindingContext = source;
```

3. Handle the `CellDoubleTap` action as a command:
   3.1. First, create a class that inherits from the `DataGridCommand` and set its `Id` property.
   3.2. Override the `CanExecute` and `Execute` methods as demonstrated in the example below.

```C#
public class CellDoubleTapUserCommand : DataGridCommand
{
    public CellDoubleTapUserCommand()
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
        var cellTap =  $"You tapped on {context.Value} inside {context.Column.HeaderText} column \n";
        Application.Current.MainPage.DisplayAlert("CellTap Command: ", cellTap, "OK");
        this.Owner.CommandService.ExecuteDefaultCommand(DataGridCommandId.CellTap, parameter);
    }
}
```

4. Add the `CellDoubleTapUserCommand` command to the `Commands` collection of the `RadDataGrid` instance:

```C#
grid.Commands.Add(new CellDoubleTapUserCommand());
```

5. Define the DataGrid in XAML:

```XAML
<telerik:RadDataGrid x:Name="grid" ItemsSource="{Binding}"/>
```

6. Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```





