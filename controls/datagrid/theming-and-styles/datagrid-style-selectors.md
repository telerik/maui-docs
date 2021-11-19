---
title: Style Selectors
page_title: .NET MAUI DataGrid Documentation | Style Selectors
description: Check our &quot;Style Selectors&quot; documentation article for Telerik DataGrid for .NET MAUI control.
position: 2
slug: datagrid-style-selectors
---

# Style Selectors

The DataGrid component exposes a conditional styling feature. It allows users to apply different styles on a cell or per group header depending on a specific condition.

You can set a different style on a specific cell from a specific column based on custom selection logic with the following properties:

* `CellContentStyleSelector`&mdash;Styles the content of the cell by using the text alignment options (`TextMargin`, `HorizontalTextAlignment`, `VerticalTextAlignment`), the font options (`FontAttributes`, `FontFamily`, `FontSize`) and the `TextColor` property.
* `CellDecorationStyleSelector`&mdash;Styles the decoration of a cell.

Different styles can be applied on a per-group header once the DataGrid control is grouped through `GroupHeaderStyleSelector` property.

The `CellContentStyleSelector`, `CellDecorationStyleSelector`, and `GroupStyleSelector` use the `SelectStyle` method to change the style.

## Example

The following example will demonstrate how to apply the style selectors in the DataGrid control:

Let’s add the DataGrid and set the `CellContentStyleSelector` as a static resource of type `MyCellContentStyleSelector`, `CellDecorationStyleSelector` as a static resource of type `MyCellDecorationStyleSelector`, and `GroupStyleSelector` as a static resource of type `MyGroupStyleSelector`.

Here is an example:

<snippet id='datagrid-styleselector-example'/>
```XAML
<telerikDataGrid:RadDataGrid x:Name="dataGrid"
							 ItemsSource="{Binding Items}"
							 AutoGenerateColumns="False"
							 GroupHeaderStyleSelector="{StaticResource MyGroupSelector}"
							 UserEditMode="Cell">
	<telerikDataGrid:RadDataGrid.Columns>
		<telerikDataGrid:DataGridTextColumn PropertyName="Country" />
		<telerikDataGrid:DataGridTextColumn PropertyName="Capital"
											CellContentStyleSelector="{StaticResource MyCellContentStyleSelector}"
											CellDecorationStyleSelector="{StaticResource MyCellDecorationSelector}" />
	</telerikDataGrid:RadDataGrid.Columns>
</telerikDataGrid:RadDataGrid>
```

Now, create a simple data for the DataGrid:

<snippet id='datagrid-styleselector-data'/>
```C#
public class Data
{
	public string Country { get; set; }
	public string Capital { get; set; }
}
```

Set the `ViewModel` class:

<snippet id='datagrid-styleselector-items'/>
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
			new Data { Country = "Singapore", Capital = "Singapore" },
			new Data { Country = "Romania", Capital = "Bucharest" },
			new Data { Country = "Spain", Capital = "Madrid" },
			new Data { Country = "France", Capital = "Paris" },
			new Data { Country = "Japan", Capital = "Tokyo" }
		};
	}

	public ObservableCollection<Data> Items { get; set; }
}
```

As a next step, add `MyCellContentStyleSelector`, `MyCellDecorationStyleSelector`, and `MyGroupStyleSelector` as resources in the **Resource** page of the application:

<snippet id='datagrid-styleselectors'/>
```XAML
<local:MyGroupSelector x:Key="MyGroupSelector">
	<local:MyGroupSelector.CountryTemplate1>
		<telerikDataGrid:DataGridGroupHeaderStyle BackgroundColor="LightYellow"
												  TextColor="Black"/>
	</local:MyGroupSelector.CountryTemplate1>
	<local:MyGroupSelector.CountryTemplate2>
		<telerikDataGrid:DataGridGroupHeaderStyle BackgroundColor="LightSkyBlue"
											      TextColor="Red"/>
	</local:MyGroupSelector.CountryTemplate2>
</local:MyGroupSelector>

<local:MyCellContentSelector x:Key="MyCellContentStyleSelector">
    <local:MyCellContentSelector.CellTemplate1>
        <telerikDataGrid:DataGridTextCellStyle TextColor="DarkOliveGreen"/>
    </local:MyCellContentSelector.CellTemplate1>
    <local:MyCellContentSelector.CellTemplate2>
        <telerikDataGrid:DataGridTextCellStyle TextColor="DarkRed"/>
    </local:MyCellContentSelector.CellTemplate2>
</local:MyCellContentSelector>

<local:MyCellDecorationSelector x:Key="MyCellDecorationSelector">
    <local:MyCellDecorationSelector.CellTemplate1>
        <telerikDataGrid:DataGridBorderStyle BackgroundColor="LightBlue"/>
    </local:MyCellDecorationSelector.CellTemplate1>
    <local:MyCellDecorationSelector.CellTemplate2>
        <telerikDataGrid:DataGridBorderStyle BackgroundColor="CadetBlue"/>
    </local:MyCellDecorationSelector.CellTemplate2>
</local:MyCellDecorationSelector>
```

Create a custom class for each selector. This class derives from `DataGridStyleSelector` and overrides its `SelectStyle` method.

The `MyCellContentStyleSelector` class implementation is as follows:

<snippet id='datagrid-styleselector-cellcontent'/>
```C#
class MyCellContentSelector &mdash;DataGridStyleSelector
{
    public DataGridStyle CellTemplate1 { get; set; }
    public DataGridStyle CellTemplate2 { get; set; }

    public override DataGridStyle SelectStyle(object item, BindableObject container)
    {
        DataGridCellInfo cellInfo = item as DataGridCellInfo;
        if (cellInfo != null)
        {
            if ((cellInfo.Item as Data).Capital == "Singapore")
            {
                return CellTemplate1;
            }
            else
            {
                return CellTemplate2;
            }
        }
        return base.SelectStyle(item, container);
    }
}
```

The implementation of the `MyCellDecorationStyleSelector` class is shown below:

<snippet id='datagrid-styleselector-celldecoration'/>
```C#
class MyCellDecorationSelector : DataGridStyleSelector
{
    public DataGridStyle CellTemplate1 { get; set; }
    public DataGridStyle CellTemplate2 { get; set; }
    public override DataGridStyle SelectStyle(object item, BindableObject container)
    {
        DataGridCellInfo cellInfo = item as DataGridCellInfo;
        if (cellInfo != null)
        {
            if ((cellInfo.Item as Data).Capital == "Singapore")
            {
                return CellTemplate1;
            }
            else
            {
                return CellTemplate2;
            }
        }
        return base.SelectStyle(item, container);
    }
}
```

You can implement `MyGroupStyleSelector` as follows:

<snippet id='datagrid-styleselector-group'/>
```C#
class MyGroupSelector : DataGridStyleSelector
{
    public DataGridStyle CountryTemplate1 { get; set; }
    public DataGridStyle CountryTemplate2 { get; set; }
    public override DataGridStyle SelectStyle(object item, BindableObject container)
    {
        GroupHeaderContext header = item as GroupHeaderContext;
        if (header != null)
        {
            if (header.Group.Key == "India")
            {
                return CountryTemplate1;
            }
            else
            {
                return CountryTemplate2;
            }
        }
        return null;
    }
}
```

This is how the DataGrid control will look when `CellContentStyleSelector` is applied.

![DataGrid StyleSelectors](../images/datagrid-style-selector.png)

## See Also

- [DataGrid Styling]({%slug datagrid-styling%})
- [Columns Styling]({%slug datagrid-columns-styling%})
