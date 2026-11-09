---
title: Tooltip
page_title: .NET MAUI PieChart Documentation - Tooltip
description: Learn how to display and customize PieSeries and DonutSeries tooltips with ChartTooltipBehavior in Telerik UI for .NET MAUI PieChart.
components: ["charts"]
tags: charts, pie chart, donut, tooltip, chart tooltip behavior, .net maui, ui for .net maui
position: 3
slug: charts-pie-tooltip
---

# .NET MAUI PieChart Tooltip

The Telerik UI for .NET MAUI PieChart displays a tooltip with information about a slice when you add a `ChartTooltipBehavior` to the `ChartBehaviors` collection of the chart. The tooltip works with the `PieSeries` and the `DonutSeries`.

## Enable the Tooltip

Add a `ChartTooltipBehavior` to the `ChartBehaviors` collection of the `RadPieChart`:

```XAML
<charts:RadPieChart x:Name="chart">
    <charts:RadPieChart.ChartBehaviors>
        <charts:ChartTooltipBehavior x:Name="tooltipBehavior"
                                     TooltipOpening="OnTooltipOpening" />
    </charts:RadPieChart.ChartBehaviors>
</charts:RadPieChart>
```

Add the `charts` namespace:

```XAML
xmlns:charts="clr-namespace:Telerik.Maui.Controls.Charts;assembly=Telerik.Maui.Controls"
```

@[template](/_contentTemplates/controls/charts.md#charts-tooltip-display-position-format)

## Events

The `ChartTooltipBehavior` exposes the `TooltipOpening` event, which is raised before the tooltip opens. The `ChartTooltipOpeningEventArgs` expose the `Series`, `SeriesIndex`, `PointIndex`, `DataItem`, `Value`, `Category`, `FormattedValue`, and `SeriesColor` properties, and the `AdditionalData` property, which you can set to pass custom data to the `TooltipContentTemplate`.

The following example calculates the difference between the actual value and a target value and passes it to the tooltip:

```C#
private void OnTooltipOpening(object sender, ChartTooltipOpeningEventArgs e)
{
    if (e.DataItem is not PieDonutTooltipPoint point)
    {
        return;
    }

    double percentage = ((point.Value - point.Target) / point.Target) * 100.0;
    string sign = percentage >= 0.0 ? "+" : string.Empty;
    string formattedPercentage = percentage.ToString("0", CultureInfo.InvariantCulture);
    e.AdditionalData = new PieDonutTooltipInfo($"{sign}{formattedPercentage}% vs target");
}

public sealed record PieDonutTooltipPoint(string Category, double Value, double Target, string Region, int Units);

public sealed record PieDonutTooltipInfo(string VsTarget);
```

## Styling the Tooltip

@[template](/_contentTemplates/controls/charts.md#charts-tooltip-style)

```XAML
<Style x:Key="TooltipStyle"
       TargetType="charts:ChartTooltip">
    <Setter Property="BackgroundColor" Value="#E8F5E9" />
    <Setter Property="BorderColor" Value="#2E7D32" />
    <Setter Property="BorderThickness" Value="1" />
    <Setter Property="CornerRadius" Value="8" />
    <Setter Property="ContentPadding" Value="12,8" />
    <Setter Property="TextColor" Value="#1B5E20" />
</Style>
```

```C#
this.tooltipBehavior.TooltipStyle = (Style)this.Resources["TooltipStyle"];
```

## Customizing the Tooltip Content

Use the `TooltipContentTemplate` property to define custom content. The following template displays the series color and name, properties from the business object, the formatted value, and the `AdditionalData` set in the `TooltipOpening` event:

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
        <VerticalStackLayout BindingContext="{Binding DataItem}"
                             x:DataType="local:PieDonutTooltipPoint"
                             Spacing="2">
            <Label Text="{Binding Category}"
                   FontSize="12" />
            <Label Text="{Binding Region}" />
            <Label Text="{Binding Units, StringFormat='Units: {0}'}" />
        </VerticalStackLayout>
        <Label Text="{Binding FormattedValue}"
               FontSize="18"
               FontAttributes="Bold" />
        <VerticalStackLayout BindingContext="{Binding AdditionalData}"
                             x:DataType="local:PieDonutTooltipInfo">
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
                        Value="{Binding TextColor, Source={RelativeSource AncestorType={x:Type charts:ChartTooltip}}, x:DataType=charts:ChartTooltip}" />
                <Setter Property="FontSize"
                        Value="{Binding FontSize, Source={RelativeSource AncestorType={x:Type charts:ChartTooltip}}, x:DataType=charts:ChartTooltip}" />
                <Setter Property="FontFamily"
                        Value="{Binding FontFamily, Source={RelativeSource AncestorType={x:Type charts:ChartTooltip}}, x:DataType=charts:ChartTooltip}" />
                <Setter Property="FontAttributes"
                        Value="{Binding FontAttributes, Source={RelativeSource AncestorType={x:Type charts:ChartTooltip}}, x:DataType=charts:ChartTooltip}" />
            </Style>
        </Grid.Resources>
        <telerik:RadBorder BackgroundColor="#F3E5F5"
                           BorderColor="#7B1FA2"
                           BorderThickness="2"
                           CornerRadius="12">
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

- [Pie Series]({% slug charts-pie-series %})
- [CartesianChart Tooltip]({% slug charts-cartesian-tooltip %})
