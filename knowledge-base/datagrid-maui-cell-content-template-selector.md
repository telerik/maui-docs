---
title: Implementing Cell Content Template Selector in DataGrid for MAUI
description: Learn how to use a DataTemplateSelector for cell content in DataGrid for MAUI to display different templates based on data conditions.
type: how-to
page_title: Using DataTemplateSelector in DataGrid for MAUI Cells
slug: datagrid-maui-cell-content-template-selector
tags: datagrid, maui, cell, template, selector, datatemplateselector
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 9.0.0 | Telerik UI for .NET MAUI DataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)|

## Description

Customizing the appearance of cell content in the DataGrid based on specific data conditions is a common requirement. This knowledge base article demonstrates how to implement a [`DataTemplateSelector`](https://learn.microsoft.com/en-us/dotnet/maui/fundamentals/datatemplate?view=net-maui-9.0#create-a-datatemplateselector) for cell content in DataGrid for MAUI. 

This knowledge base article also answers the following questions:
- How do I use a `DataTemplateSelector` with DataGrid in MAUI?
- Can I display different cell templates in DataGrid based on the data?
- What is the way to customize DataGrid cells dynamically in MAUI?

## Solution

To customize cell content dynamically in the DataGrid, use a `DataTemplateSelector`. This requires defining multiple `DataTemplate` instances and a selector class that decides which template to apply based on the data.

### Step 1: Define the Data Templates

Define the data templates in the XAML resources. Each template specifies how the cell content should appear for different data conditions.

```xml
<ContentPage.Resources>
    <ResourceDictionary>
        <DataTemplate x:Key="validPersonTemplate">
            <Grid>
                <Entry Text="{Binding Country}" BackgroundColor="LightBlue" />
            </Grid>
        </DataTemplate>
        <DataTemplate x:Key="invalidPersonTemplate">
            <Grid>
                <Button Text="{Binding Country}" BackgroundColor="Red"/>
            </Grid>
        </DataTemplate>

        <local:PersonDataTemplateSelector x:Key="personDataTemplateSelector"
                                          ValidTemplate="{StaticResource validPersonTemplate}"
                                          InvalidTemplate="{StaticResource invalidPersonTemplate}" />
    </ResourceDictionary>
</ContentPage.Resources>
```

### Step 2: Implement the DataTemplateSelector

Create a `DataTemplateSelector` subclass that overrides the `OnSelectTemplate` method. This method determines which template to use based on the data condition.

```csharp
public class PersonDataTemplateSelector : DataTemplateSelector
{
    public DataTemplate ValidTemplate { get; set; }
    public DataTemplate InvalidTemplate { get; set; }

    protected override DataTemplate OnSelectTemplate(object item, BindableObject container)
    {
        return ((Data)item).Country == "India" ? ValidTemplate : InvalidTemplate;
    }
}
```

### Step 3: Define sample model and ViewModel:

```csharp
public class ViewModel
{
    public ObservableCollection<Data> Items { get; set; }
    public ViewModel()
    {

        this.Items = new ObservableCollection<Data>()
        {
                new Data { Country = "India", Capital = "New Delhi"},
                new Data { Country = "South", Capital = "Cape Town"},
                new Data { Country = "Nigeria", Capital = "Abuja"},
                new Data { Country = "Singapore", Capital = "Singapore"}
        };
    }
}
public class Data
{
    public string Country { get; set; }
    public string Capital { get; set; }
}
```

### Step 4: Apply the Template Selector to the DataGrid

Assign the template selector to the `CellContentTemplateSelector` property of the relevant DataGrid column.

```xml
<telerik:RadDataGrid x:Name="dataGrid" 
                 ItemsSource="{Binding Items}" 
                 AutoGenerateColumns="False" 
                 UserEditMode="Cell">
    <telerik:RadDataGrid.Columns>
        <telerik:DataGridTextColumn PropertyName="Name" 
                                    Width="130"
                                    SizeMode="Fixed"
                                    HeaderText="Name"
                                    CellContentTemplateSelector="{StaticResource personDataTemplateSelector}"/>
        <telerik:DataGridTextColumn PropertyName="Capital" />
    </telerik:RadDataGrid.Columns>
</telerik:RadDataGrid>
```

This setup allows the DataGrid to dynamically display different cell templates based on the condition defined in the `PersonDataTemplateSelector`.

## See Also

- [Data Templates in .NET MAUI](https://learn.microsoft.com/en-us/dotnet/maui/fundamentals/datatemplate)
- [DataGrid Overview in Telerik UI for MAUI](https://docs.telerik.com/devtools/maui/controls/datagrid/overview)
