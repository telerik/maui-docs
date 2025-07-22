---
title: Implement Selection Column for DataGrid
description: Learn how to add a selection column to the DataGrid in .NET MAUI so the user can select the entire row using or select all rows.
type: how-to
page_title: How to Create a Selection Column For Row selection in the RadDataGrid for .NET MAUI
slug: datagrid-selection-column
tags: datagrid, .net maui, selection, row, checkbox
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 7.1.0 | Telerik UI for .NET MAUI DataGrid | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

## Description

In a .NET MAUI application, you may want to select a DataGrid row through a column or all grid rows from the header of this column.

## Solution

To implement such a column and to avoid the usage of the templates, use the [Cell Renderer]({%slug datagrid-render-mode%}) approach. This approach uses SkiaSharp to draw the elements inside the DataGrid cell. In such scenarios, use a `DataGridBooleanColumn` with a Skia `CellRenderer`. The cell renderer will draw a checkbox element in the cell.

Here is the implementation:

1. Draw a `CheckBox` using the `CellRenderer` approach. 

    1.1 Create a custom `CheckboxColumnRenderer` class that inherits from `DataGridCellRenderer`. 
    
    1.2 Override the `RenderContainer` method and draw the custom control.

```C#
public class CheckboxColumnRenderer : DataGridCellRenderer
{
    protected override void RenderContainer(DataGridCellRendererRenderContext renderContext)
    {
        EmployeeDto club = (EmployeeDto)renderContext.Item;

        if (renderContext is DataGridSkiaSharpCellRendererRenderContext skRenderContext)
        {
            this.DrawCheckBox(club.OnLeave, skRenderContext, skRenderContext.Bounds);
        }
    }

    private void DrawCheckBox(bool isChecked, DataGridSkiaSharpCellRendererRenderContext skRenderContext, Rect bounds)
    {
        double horizontalPadding = 8;
        double x = bounds.X + horizontalPadding;
        double h = 20;
        double y = bounds.Y + (bounds.Height - h) / 2;
        double displayScale = skRenderContext.DisplayScale;

        // Reusing Height for the width so the checkbox is square
        Rect rect = new Rect(x, y, h, h);

        var skiaRect = SkiaUtils.ToSKRect(rect, displayScale);

        // checkbox border
        using var paint = new SKPaint();
        paint.Style = SKPaintStyle.Stroke;
        paint.Color = SKColors.Black;
        paint.StrokeWidth = 2;
        skRenderContext.Canvas.DrawRect(skiaRect, paint);

        if (isChecked)
        {
            // checkmark
            using var checkMarkPaint = new SKPaint();
            checkMarkPaint.Style = SKPaintStyle.Stroke;
            checkMarkPaint.Color = SKColors.Black;
            checkMarkPaint.StrokeWidth = 2;

            var path = new SKPath();
            path.MoveTo(skiaRect.Left + 4, skiaRect.MidY);
            path.LineTo(skiaRect.MidX, skiaRect.Bottom - 4);
            path.LineTo(skiaRect.Right - 4, skiaRect.Top + 4);
            skRenderContext.Canvas.DrawPath(path, checkMarkPaint);
        }
    }

    internal static class SkiaUtils
    {
        public static SKRect ToSKRect(Rect rect, double scale = 1)
        {
            return new SKRect((float)(scale * rect.Left), (float)(scale * rect.Top), (float)(scale * rect.Right), (float)(scale * rect.Bottom));
        }

        public static Rect ToRect(SKRect skRect, double scale = 1)
        {
            return new Rect(scale * skRect.Left, scale * skRect.Top, scale * skRect.Right, scale * skRect.Bottom);
        }
    }
}
```


2. In the XAML, set the custom `CheckboxColumnCellRenderer` class to the `DataGridBooleanColumn.CellRenderer` property:

```XAML
<ContentPage.Resources>
    <local:CheckboxColumnRenderer x:Key="CheckboxColumnCellRenderer" />
</ContentPage.Resources>

<Grid>
    <telerik:RadDataGrid x:Name="EmployeesGrid"
                         RenderMode="SkiaSharp"
                         ItemsSource="{Binding Employees}"
                         AutoGenerateColumns="False">
        <telerik:RadDataGrid.Columns>
            <telerik:DataGridBooleanColumn PropertyName="OnLeave"
                                           CellRenderer="{StaticResource CheckboxColumnCellRenderer}">
                <telerik:DataGridBooleanColumn.HeaderStyle>
                    <telerik:DataGridColumnHeaderStyle TextMargin="0"
                                                        FilterIndicatorMargin="0"
                                                        BorderThickness="0" />
                </telerik:DataGridBooleanColumn.HeaderStyle>
                <telerik:DataGridBooleanColumn.HeaderContentTemplate>
                    <DataTemplate>
                        <Grid>
                            <telerik:RadCheckBox IsChecked="{Binding BindingContext.AreAllItemsChecked, Mode=TwoWay, Source={x:Reference EmployeesGrid}}"
                                                    CornerRadius="0"
                                                    StrokeWidth="2"
                                                    CheckedColor="Black"
                                                    Margin="5,0,0,0"
                                                    HeightRequest="30"
                                                    WidthRequest="30" />
                        </Grid>
                    </DataTemplate>
                </telerik:DataGridBooleanColumn.HeaderContentTemplate>
            </telerik:DataGridBooleanColumn>
            <telerik:DataGridTextColumn PropertyName="Name"
                                        HeaderText="Name" />
            <telerik:DataGridNumericalColumn PropertyName="Position"
                                                HeaderText="Position" />
        </telerik:RadDataGrid.Columns>
    </telerik:RadDataGrid>
</Grid>
```

3. Add a sample data model:

```C#
public class EmployeeDto : Employee
{
    private bool onLeave;

    public EmployeeDto(Employee source)
    {
        this.Name = source.Name;
        this.Position = source.Position;
        this.Salary = source.Salary;
        this.StartDate = source.StartDate;
        this.VacationTotal = source.VacationTotal;
        this.VacationUsed = source.VacationUsed;
    }

    public bool OnLeave
    {
        get => onLeave;
        set => SetProperty(ref onLeave, value);
    }
}
```

4. Add the `ViewModel`:

```C#
public class MainViewModel : ViewModelBase
{
    private ObservableRangeCollection<EmployeeDto> employees;

    public MainViewModel()
    {
        Employees = new ObservableRangeCollection<EmployeeDto>(SampleDataService.Current.GenerateEmployeeData()
            .Select(e => new EmployeeDto(e))
            .Take(40));
    }

    public ObservableRangeCollection<EmployeeDto> Employees
    {
        get => employees;
        set => SetProperty(ref employees, value);
    }

    public bool AreAllItemsChecked
    {
        get => Employees.All(e => e.OnLeave);
        set
        {
            foreach (var employeeDto in Employees) 
                employeeDto.OnLeave = value;
        }
    }
}
```

This is the result:

![.NET MAUI DataGrid Selection Column](images/datagrid-selection-column.png)