---
title: Tooltip
page_title: .NET MAUI CartesianChart Documentation - Tooltip
description: Learn how to display and customize tooltips for the data points of the Telerik UI for .NET MAUI CartesianChart series by using the ChartTooltipBehavior.
components: ["charts"]
tags: charts, cartesian chart, tooltip, chart tooltip behavior, .net maui, ui for .net maui
position: 10
slug: charts-cartesian-tooltip
---

# .NET MAUI CartesianChart Tooltip

The Telerik UI for .NET MAUI CartesianChart displays a tooltip with information about a data point when you add a `ChartTooltipBehavior` to the `ChartBehaviors` collection of the chart. The tooltip works with all Cartesian series: `AreaSeries`, `BarSeries`, `CandlestickSeries`, `LineSeries`, `OhlcSeries`, `PointSeries`, `SplineAreaSeries`, and `SplineSeries`.

## Enable the Tooltip

Add a `ChartTooltipBehavior` to the `ChartBehaviors` collection of the `RadCartesianChart`:

```XAML
<charts:RadCartesianChart x:Name="chart">
    <charts:RadCartesianChart.ChartBehaviors>
        <charts:ChartTooltipBehavior x:Name="tooltipBehavior"
                                     TooltipOpening="OnTooltipOpening" />
    </charts:RadCartesianChart.ChartBehaviors>
    <charts:RadCartesianChart.Axes>
        <charts:CategoricalAxis x:Name="categoricalAxis"
                                Location="Bottom" />
        <charts:NumericalAxis x:Name="numericalAxis"
                              Location="Left" />
    </charts:RadCartesianChart.Axes>
</charts:RadCartesianChart>
```

Add the `charts` namespace:

```XAML
xmlns:charts="clr-namespace:Telerik.Maui.Controls.Charts;assembly=Telerik.Maui.Controls"
```

@[template](/_contentTemplates/controls/charts.md#charts-tooltip-display-position-format)

## Events

The `ChartTooltipBehavior` exposes the `TooltipOpening` event, which is raised before the tooltip opens. The TooltipOpening event provides two parameters:
* The sender, which is of type object.
* The `ChartTooltipOpeningEventArgs`, which provides information about the `Series`, `SeriesIndex`, `PointIndex`, `DataItem`, `Value`, `Category`, `FormattedValue`, and `SeriesColor` properties, and the `AdditionalData` property.

The following example calculates the difference between the actual value and a target value and passes it to the tooltip:

```C#
private void OnTooltipOpening(object sender, ChartTooltipOpeningEventArgs e)
{
    if (e.DataItem is not CartesianTooltipPoint point)
    {
        return;
    }

    double percentage = ((point.Value - point.Target) / point.Target) * 100.0;
    string sign = percentage >= 0.0 ? "+" : string.Empty;
    string formattedPercentage = percentage.ToString("0", CultureInfo.InvariantCulture);
    e.AdditionalData = new CartesianTooltipInfo($"{sign}{formattedPercentage}% vs target");
}
```


## Styling the Tooltip

@[template](/_contentTemplates/controls/charts.md#charts-tooltip-style)

```XAML
<Style x:Key="TooltipStyle"
       TargetType="charts:ChartTooltip">
    <Setter Property="BackgroundColor" Value="#FFF3E0" />
    <Setter Property="BorderColor" Value="#E65100" />
    <Setter Property="BorderThickness" Value="1" />
    <Setter Property="CornerRadius" Value="8" />
    <Setter Property="ContentPadding" Value="12,8" />
    <Setter Property="TextColor" Value="#4E342E" />
</Style>
```

```C#
this.tooltipBehavior.TooltipStyle = (Style)this.Resources["TooltipStyle"];
```

## Customizing the Tooltip Content

Use the `TooltipContentTemplate` property to define custom content. The following template displays the series color and name, the category, properties from the business object, the formatted value, and the `AdditionalData` set in the `TooltipOpening` event:

```XAML
<DataTemplate x:Key="TooltipContentTemplate"
              x:DataType="charts:ChartTooltipContext">
    <VerticalStackLayout Spacing="6">
        <HorizontalStackLayout Spacing="8">
            <BoxView Color="{Binding SeriesColor}"
                     WidthRequest="12"
                     HeightRequest="12"
                     VerticalOptions="Center" />
            <Label Text="{Binding Series.DisplayName}"
                   FontAttributes="Bold"
                   VerticalOptions="Center" />
        </HorizontalStackLayout>
        <VerticalStackLayout Spacing="2">
            <Label Text="{Binding Category, StringFormat='{}{0:MMM d}'}"
                   FontSize="12" />
            <VerticalStackLayout BindingContext="{Binding DataItem}"
                                 x:DataType="local:CartesianTooltipPoint"
                                 Spacing="2">
                <Label Text="{Binding Region}" />
                <Label Text="{Binding Units, StringFormat='Units: {0}'}" />
            </VerticalStackLayout>
        </VerticalStackLayout>
        <Label Text="{Binding FormattedValue}"
               FontSize="18"
               FontAttributes="Bold" />
        <VerticalStackLayout BindingContext="{Binding AdditionalData}"
                             x:DataType="local:CartesianTooltipInfo">
            <Label Text="{Binding VsTarget}"
                   FontAttributes="Bold" />
        </VerticalStackLayout>
    </VerticalStackLayout>
</DataTemplate>
```

```C#
this.tooltipBehavior.TooltipContentTemplate = (DataTemplate)this.Resources["TooltipContentTemplate"];
```

## Customizing the Tooltip Control Template

To fully change the tooltip appearance, set the `ControlTemplate` property of the `ChartTooltip` through the `TooltipStyle`. Use a `ContentPresenter` to display the tooltip content, and bind to the `ChartTooltip` text properties through a `RelativeSource` binding:

```XAML
<ControlTemplate x:Key="TooltipControlTemplate">
    <Grid>
        <Grid.Resources>
            <Style TargetType="Label">
                <Setter Property="TextColor"
                        Value="Black" />
                <Setter Property="FontSize"
                        Value="{Binding FontSize, Source={RelativeSource AncestorType={x:Type charts:ChartTooltip}}, x:DataType=charts:ChartTooltip}" />
                <Setter Property="FontFamily"
                        Value="{Binding FontFamily, Source={RelativeSource AncestorType={x:Type charts:ChartTooltip}}, x:DataType=charts:ChartTooltip}" />
                <Setter Property="FontAttributes"
                        Value="{Binding FontAttributes, Source={RelativeSource AncestorType={x:Type charts:ChartTooltip}}, x:DataType=charts:ChartTooltip}" />
            </Style>
        </Grid.Resources>
        <telerik:RadBorder BackgroundColor="#E3F2FD"
                            BorderColor="#1565C0"
                            BorderThickness="2"
                            CornerRadius="8">
            <ContentPresenter Margin="10" />
        </telerik:RadBorder>
    </Grid>
</ControlTemplate>

<Style x:Key="TooltipControlTemplateStyle"
        TargetType="charts:ChartTooltip">
    <Setter Property="ControlTemplate" Value="{StaticResource TooltipControlTemplate}" />
</Style>
```

```C#
this.tooltipBehavior.TooltipStyle = (Style)this.Resources["TooltipControlTemplateStyle"];
```


## See Also

- [Data Point Labels]({% slug charts-cartesian-data-point-labels %})
- [PieChart Tooltip]({% slug charts-pie-tooltip %})
