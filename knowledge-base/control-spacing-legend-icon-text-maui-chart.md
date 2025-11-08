---
title: Adjusting Spacing Between Legend Icon and Text in Telerik UI for .NET MAUI Pie Chart
description: Learn how to control the spacing between the legend icon and text in the Pie Chart of Telerik UI for .NET MAUI.
type: how-to
page_title: Control Spacing Between Legend Icon and Text in .NET MAUI Chart
meta_title: Control Spacing Between Legend Icon and Text in .NET MAUI Chart
slug: control-spacing-legend-icon-text-maui-chart
tags: chart, ui for .net maui, legend, spacing, collectionview
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.1.0 | Telerik UI for .NET MAUI Chart | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to control the spacing between the legend icon and the legend text when using the [Pie Chart](https://www.telerik.com/maui-ui/documentation/controls/chart/types/pie-chart) in Telerik UI for .NET MAUI. By default, the icons and text appear very close together.

This knowledge base article also answers the following questions:

- How to customize the legend layout in Telerik UI for .NET MAUI Chart?
- How to use CollectionView for controlling legend spacing in Charts?
- How to adjust legend appearance in .NET MAUI Chart?

## Solution

To control the spacing between the legend icon and text, use the Telerik MAUI CollectionView and define a custom layout for the legend. Follow these steps:

1. Add a `RadCollectionView` to your layout and configure its `ItemsLayout` with the desired spacing using `CollectionViewLinearLayout`.
2. Define a custom `ItemTemplate` in the `RadCollectionView`.
3. Use a `HorizontalStackLayout` with the `Spacing` property to control the distance between the legend icon and text.

```xaml
<ContentPage.Resources>
    <ResourceDictionary>
        <Style TargetType="telerik:RadCollectionViewItemView">
            <Setter Property="BorderThickness" Value="0" />
            <Setter Property="BorderColor" Value="Transparent" />
        </Style>
    </ResourceDictionary>
</ContentPage.Resources>

<Grid RowDefinitions="400,100">
    <telerik:RadPieChart x:Name="chartTest" Loaded="ChartTest_OnLoaded">
        <telerik:RadPieChart.Palette>
            <telerik:ChartPalette>
                <telerik:ChartPalette.Entries>
                    <telerik:PaletteEntry FillColor="#4FB6E7" StrokeColor="#4FB6E7" />
                    <telerik:PaletteEntry FillColor="#A666CE" StrokeColor="#A666CE" />
                    <telerik:PaletteEntry FillColor="#9DCC00" StrokeColor="#9DCC00" />
                </telerik:ChartPalette.Entries>
            </telerik:ChartPalette>
        </telerik:RadPieChart.Palette>
        <telerik:RadPieChart.Series>
            <telerik:PieSeries ShowLabels="True" RadiusFactor="0.8" ValueBinding="Value" ItemsSource="{Binding Data}" />
        </telerik:RadPieChart.Series>
    </telerik:RadPieChart>

    <telerik:RadCollectionView SelectionMode="None" x:Name="LegendItemsControl" Grid.Row="1">
        <telerik:RadCollectionView.ItemsLayout>
            <telerik:CollectionViewLinearLayout Orientation="Horizontal" ItemSpacing="15" />
        </telerik:RadCollectionView.ItemsLayout>
        <telerik:RadCollectionView.ItemTemplate>
            <DataTemplate x:DataType="local:LegendItem">
                <HorizontalStackLayout Spacing="15">
                    <telerik:RadBorder BackgroundColor="{Binding SeriesPaletteEntry.FillColor}" WidthRequest="40" HeightRequest="40" />
                    <Label Text="{Binding SeriesDisplayName}" FontSize="12" VerticalOptions="Center" FontAttributes="Bold" />
                </HorizontalStackLayout>
            </DataTemplate>
        </telerik:RadCollectionView.ItemTemplate>
    </telerik:RadCollectionView>
</Grid>
```

4. Bind the legend items to the `RadCollectionView` in the code-behind.

```csharp
public partial class MainPage : ContentPage
{
    private readonly ObservableCollection<LegendItem> legendItems = new();
    
    public MainPage()
    {
        InitializeComponent();
        this.BindingContext = new ViewModel();
        this.LegendItemsControl.ItemsSource = legendItems;
    }

    private void ChartTest_OnLoaded(object sender, EventArgs e)
    {
        foreach (var series in chartTest.Series)
        {
            var source = (ObservableCollection<CategoricalData>)series.ItemsSource;
            foreach (var item in source)
            {
                var displayName = item.Category;
                var colorIndex = source.IndexOf(item) % chartTest.Palette.Entries.Count;
                this.legendItems.Add(new LegendItem
                {
                    SeriesPaletteEntry = chartTest.Palette.Entries[colorIndex],
                    SeriesDisplayName = displayName.ToString(),
                });
            }
        }
    }
}
```

5. Add a sample `ViewModel`, `DataItem` and `LegendItem`:

```csharp
public class ViewModel
{
    public ObservableCollection<CategoricalData> Data { get; set; }

    public ViewModel()
    {
        this.Data = GetCategoricalData();
    }

    private static ObservableCollection<CategoricalData> GetCategoricalData()
    {
        return new ObservableCollection<CategoricalData>
        {
            new CategoricalData { Category = "Greenings", Value = 52 },
            new CategoricalData { Category = "Perfecto", Value = 19 },
            new CategoricalData { Category = "NearBy", Value = 82 },
            new CategoricalData { Category = "Family", Value = 23 },
            new CategoricalData { Category = "Fresh", Value = 56 },
        };
    }
}

public class CategoricalData
{
    public object Category { get; set; }
    public double Value { get; set; }
}

public class LegendItem : NotifyPropertyChangedBase
{
    private string seriesDisplayName;
    private PaletteEntry seriesPaletteEntry;

    public PaletteEntry SeriesPaletteEntry
    {
        get => seriesPaletteEntry;
        set => UpdateValue(ref seriesPaletteEntry, value);
    }

    public string SeriesDisplayName
    {
        get => seriesDisplayName;
        set => UpdateValue(ref seriesDisplayName, value);
    }
}
```

## See Also

- [Pie Series](https://www.telerik.com/maui-ui/documentation/controls/chart/series/pie/pie-series)
