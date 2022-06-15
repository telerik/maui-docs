---
title: Events
page_title: .NET MAUI DataGrid Documentation | Events
description: Check our &quot;Events&quot; documentation article for Telerik DataGrid for .NET MAUI control.
position: 9
slug: datagrid-events-overview
description: Describing the events of the RadDataGrid
tags: events
---

# Events

The DataGrid component exposes a set of events.

## Load On Demand Events

* `IsDataLoaded`&mdash;Boolean property that is updated when the data of the `DataGrid` gets loaded. To use this property a new instance of the `LoadOnDemandEventArgs` class needs to be initialized.

## Disctinct Values Events

* `DistinctValues`&mdash; Is a property which gets or sets a list of values of type `IEnumerable` which are to be displayed in the `DataGridDistinctValuesFilterView`.
* `Column`&mdash; Is a readonly property of type `DataGridColumn` which gets the column for which the distinct values are being loaded.

## Example

The following example demonstrates the usage of the `IsDataLoaded` property&mdash;
 ```C#
private async void dataGrid_LoadOnDemand(object sender, Telerik.Maui.Controls.Compatibility.DataGrid.LoadOnDemandEventArgs e)
    {
        await Task.Delay(3000);
        for (int i = 0; i < 15; i++)
        {
            ((sender as RadDataGrid).ItemsSource as ObservableCollection<Person>).Add(new Person() { Name = "Person " + i, Age = i + 18, Gender = i % 2 == 0 ? Gender.Male : Gender.Female });
        }
        e.IsDataLoaded = true;
    }
 ```
The following example demonstrates the usage of `DistinctValues`&mdash;

Define the `DataGrid` in XAML:
 ```XAML
<telerik:RadDataGrid x:Name="dataGrid"
                             AutoGenerateColumns="False">
            <telerik:RadDataGrid.Columns>
                <telerik:DataGridComboBoxColumn x:Name="comboColumn" PropertyName="MyEnumerator" HeaderText="MyEnumerator" />
            </telerik:RadDataGrid.Columns>
        </telerik:RadDataGrid>
 ```

Define the Enumerator:
```C#
public enum Enumerator
    {
        One,
        Twoo,
        Threee,
    }
```
After declaring the Enumerator, create the list of values which are to be displayed in the `DataGridDistinctValuesFilterView` by using the `DistinctValues` property:
```C#
this.comboColumn.DistinctValues = new List<Enumerator> { Enumerator.Threee, Enumerator.Twoo, Enumerator.One };
```

## See Also

 - [Filtering]({%slug datagrid-filtering-overview%})
 - [Grouping]({%slug datagrid-grouping-overview%})
 - [Selection]({%slug datagrid-selection-overview%})
 - [Load On Demand]({%slug datagrid-features-loadondemand%})
 - [Sorting]({%slug datagrid-sorting-overview%})
 - [Row Height]({%slug datagrid-row-height%})
 - [Editing]({%slug datagrid-editing%})
