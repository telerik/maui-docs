---
title: Select Cell on Double Tap
description: Select Cell in DataGrid by Using Double Tap or Double Click
type: how-to
page_title: Cell Selection on Double Tap
slug: datagrid-cell-selection-doubletap
position: 5
ticketid: 1611664
res_type: kb
---

## Environment

| Version | Product | 
| --- | --- |
| 5.2.0 | Telerik UI for .NET MAUI DataGrid | 


## Description

This how-to article describes how to select a cell by using the double click, double tap gesture. 


## Solution

For this purpose we will execute the `CellTap` command on `CellDoubleTap` command. So when the user of the application double tapped or double-click on the cell, the item will be selected. 

Here is an example how to execute the `CellTap` command in `CellDoubleTap` command.

**1.** Create the needed business objects, for example, the `Country` type with the following properties:

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

**2.** Add data to the DataGrid `ItemsSource` and set the `BindingContext`:

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

**3.** Handle the `CellDoubleTap` action as a command:
   **3.1.** First, create a class that inherits from the `DataGridCommand` and set its `Id` property.
   **3.2.** Override the `CanExecute` and `Execute` methods as demonstrated in the example below.


```C#
    public class CellDoubleTapUserCommand : DataGridCommand
    {
        public CellDoubleTapUserCommand()
        {
            Id = DataGridCommandId.CellDoubleTap;
        }

        public override void Execute(object parameter)
        {
            this.Owner.CommandService.ExecuteDefaultCommand(DataGridCommandId.CellTap, parameter);
        }
    }
```

**4.** Handle the `CellTap` action as a command, so when you double click on the cell, to not be in edit mode.

```C#
    public class CellTapUserCommand : DataGridCommand
    {
        public CellTapUserCommand()
        {
            Id = DataGridCommandId.CellTap;
        }

        public override void Execute(object parameter)
        {
            
        }
    }
```

**5.** Add the `CellDoubleTapUserCommand` command to the `Commands` collection of the `RadDataGrid` instance:

```C#
grid.Commands.Add(new CellDoubleTapUserCommand());
```

**6.** Define the DataGrid in XAML:

```XAML
<telerik:RadDataGrid x:Name="grid" ItemsSource="{Binding}"/>
```

**7.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```





