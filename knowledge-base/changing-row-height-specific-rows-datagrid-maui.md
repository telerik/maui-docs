---
title: Changing Row Height for Specific Rows in DataGrid
description: Learn how to adjust the row height for specific rows in the DataGrid for Telerik UI for .NET MAUI using CellContentTemplateSelector and DataTemplate.
type: how-to
meta_title: Adjusting Row Height Dynamically in DataGrid for Telerik UI for .NET MAUI
slug: changing-row-height-specific-rows-datagrid-maui
tags: datagrid, rowheight, template selector, .net maui, telerik ui
res_type: kb
---

## Environment

| Version | Product | Author |
| --- | --- | ---- |
| 13.2.0 | Telerik UI for .NET MAUI DataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

I want to change the row height for specific rows in the [DataGrid](https://www.telerik.com/maui-ui/documentation/controls/datagrid/overview) for Telerik UI for .NET MAUI. The DataGrid allows setting a uniform height for all rows via the `RowHeight` property, but I need different heights based on row data.

This knowledge base article also answers the following questions:

- How do I use `DataTemplateSelector` to set dynamic row heights in DataGrid?
- Can rows in DataGrid have varying heights in Telerik UI for .NET MAUI?
- How do I create a custom row height logic for DataGrid rows?

## Solution

To set different row heights for specific rows in the DataGrid, use a `CellContentTemplateSelector` along with `DataTemplate`. Follow these steps:

1. Set up the DataGrid with a column that uses a `CellContentTemplateSelector`:

   ```xaml
   <telerik:RadDataGrid x:Name="dataGrid"
                        ItemsSource="{Binding Employees}"
                        AutoGenerateColumns="False"
                        SelectionMode="Single"
                        Margin="8">
       <telerik:RadDataGrid.Columns>
           <telerik:DataGridTextColumn PropertyName="Name" HeaderText="Name" SizeMode="Stretch" />
           <telerik:DataGridTextColumn PropertyName="Department" HeaderText="Department" SizeMode="Fixed" Width="120" />
           <telerik:DataGridNumericalColumn PropertyName="Salary" HeaderText="Salary" SizeMode="Fixed" Width="100" />
           <telerik:DataGridTextColumn HeaderText="Status" SizeMode="Fixed" Width="100" CellContentTemplateSelector="{StaticResource StatusCellTemplateSelector}" />
       </telerik:RadDataGrid.Columns>
   </telerik:RadDataGrid>
   ```

2.  Create templates with different heights:

   ```xaml
   <!-- Template for Active employees: green badge -->
   <DataTemplate x:Key="ActiveStatusTemplate">
       <Grid>
           <Label Text="Active"
                  TextColor="Green"
                  FontAttributes="Bold"
                  FontSize="12"
                  HeightRequest="40"
                  VerticalTextAlignment="Center"
                  HorizontalOptions="Center" />
       </Grid>
   </DataTemplate>

   <!-- Template for Inactive employees: red badge -->
   <DataTemplate x:Key="InactiveStatusTemplate">
       <Grid>
           <Label Text="Inactive"
                  TextColor="Red"
                  FontAttributes="Bold"
                  FontSize="12"
                  HeightRequest="60"
                  VerticalTextAlignment="Center"
                  HorizontalOptions="Center" />
       </Grid>
   </DataTemplate>
   ```

3. Use a `DataTemplateSelector` to switch templates:

   ```xaml
   <selectors:StatusCellTemplateSelector x:Key="StatusCellTemplateSelector"
                                         ActiveTemplate="{StaticResource ActiveStatusTemplate}"
                                         InactiveTemplate="{StaticResource InactiveStatusTemplate}" />
   ```

4. Write the logic for choosing a template based on row data.

   ```csharp
   public class StatusCellTemplateSelector : DataTemplateSelector
   {
       public DataTemplate? ActiveTemplate { get; set; }
       public DataTemplate? InactiveTemplate { get; set; }

       protected override DataTemplate? OnSelectTemplate(object item, BindableObject container)
       {
           if (item is Employee employee)
               return employee.IsActive ? ActiveTemplate : InactiveTemplate;

           return ActiveTemplate;
       }
   }
   ```

5. Define the `ViewModel`:

   ```csharp
   public class MainViewModel
   {
       public ObservableCollection<Employee> Employees { get; } = new()
       {
           new Employee { Name = "Alice Johnson", Department = "Engineering", Salary = 95000, IsActive = true },
           new Employee { Name = "Bob Smith", Department = "Marketing", Salary = 72000, IsActive = false },
           new Employee { Name = "Carol Williams", Department = "Engineering", Salary = 105000, IsActive = true },
           new Employee { Name = "David Brown", Department = "HR", Salary = 68000, IsActive = false },
           new Employee { Name = "Eva Martinez", Department = "Finance", Salary = 88000, IsActive = true },
           new Employee { Name = "Frank Wilson", Department = "Engineering", Salary = 112000, IsActive = true },
           new Employee { Name = "Grace Lee", Department = "Marketing", Salary = 76000, IsActive = false },
           new Employee { Name = "Henry Taylor", Department = "Finance", Salary = 91000, IsActive = true },
       };
   }
   ```

6. Create a class to represent employee data:

   ```csharp
   public class Employee
   {
       public string Name { get; set; } = string.Empty;
       public string Department { get; set; } = string.Empty;
       public decimal Salary { get; set; }
       public bool IsActive { get; set; }
   }
   ```

## See Also

- [Row Height Documentation for Telerik UI for .NET MAUI](https://www.telerik.com/maui-ui/documentation/controls/datagrid/row-height)
- [DataGrid Cell Templates Documentation](https://www.telerik.com/maui-ui/documentation/controls/datagrid/columns/cell-templates)
