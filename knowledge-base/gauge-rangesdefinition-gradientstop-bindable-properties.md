---
title: Bindings for properties inside the RadGauge GaugeRangesDefinition and GradientStop classes
description: Learn how to apply bindings for the properties inside the GaugeRangesDefinition and GradientStop classes of the Gauge for .NET MAUI.
type: how-to
page_title: How to make the properties inside the GaugeRangesDefinition and GradientStop Bindable.
slug: gauge-rangesdefinition-gradientstop-bindable-properties
tags: gauge, ranges, bindable properties, .net maui
res_type: kb
---

## Environment

| Product | Version | Author |
| --- | --- | --- | 
| Gauge for .NET MAUI | 7.1.0 | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

When using a horizontal or vertical Gauge in a .NET MAUI application, you may want to bind the values for the offset, the color properties inside the `RadGradientStop`, or the values for the `StartThickness` and `EndThickness` for the `GaugeRangesDefinition`. This article demonstrates how to set bindings for the properties inside the `GaugeRangesDefinition` and `RadGradientStop` classes.

This KB article also answers the following questions:
- How can I set bindings for the `Offset` and `Color` properties inside the `RadGradientStop`?
- How can I set bindings for the `StartThickness` and `EndThickness` properties inside the `GaugeRangesDefinition`?

## Solution

The properties inside the `GaugeRangesDefinition` and `RadGradientStop` classes are not bindable. To apply binding, use an attached property.

The example shows how to apply binding for the `StartThickness` property inside the `GaugeRangesDefinition`. The approach is applicable for the other properties.

**1.** Define the `RadGauge` in XAML:

```XAML
<VerticalStackLayout>
	<Label Text="{Binding Value, Source={x:Reference slider}}"/>
	<Slider Value="{Binding Data, Mode=TwoWay}" x:Name="slider" Minimum="5" Maximum="40"/>

	<telerik:RadVerticalGauge x:Name="gauge">
		<telerik:RadVerticalGauge.Axis>
			<telerik:GaugeLinearAxis LabelPosition="Start"
			Maximum="1"
			Minimum="-1"
			Step="0.5" />
		</telerik:RadVerticalGauge.Axis>
		<telerik:RadVerticalGauge.Indicators>
			<telerik:GaugeShapeIndicator Value="0" />
		</telerik:RadVerticalGauge.Indicators>
		<telerik:RadVerticalGauge.Ranges>
			<telerik:GaugeRangesDefinition x:Name="range"
										   local:TelerikUtils.MyThickness="{Binding Data}">
				<telerik:GaugeGradientRange From="-1" To="1">
					<telerik:RadGradientStop
					x:Name="B"
					Offset="1"
					Color="Blue" />
					<telerik:RadGradientStop
					x:Name="R"
					Offset="0"
					Color="Red" />
					<telerik:RadGradientStop
					x:Name="O"
					Offset="-1"
					Color="orange" />
				</telerik:GaugeGradientRange>
			</telerik:GaugeRangesDefinition>
		</telerik:RadVerticalGauge.Ranges>
	</telerik:RadVerticalGauge>
</VerticalStackLayout>
```

**2.** Define a sample `ViewModel` and set it as a `BindingContext`:

```C#
public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();
        this.BindingContext = new ViewModel();
    }
}
public class ViewModel : NotifyPropertyChangedBase
{
    private double data = 10;
    public double Data
    {
        get =>this.data;
        set { this.UpdateValue(ref this.data, value);}
    }
}
```

**3.** DEfine a `TelerikUtils` class with the attached property implementation:

```C#
public static class TelerikUtils
{
	public static readonly BindableProperty MyThicknessProperty =
BindableProperty.CreateAttached("MyThickness", typeof(double), typeof(TelerikUtils), 0.0, propertyChanged: OnMyThicknessChanged);

	public static double GetMyThickness(BindableObject bindable)
	{
		return (double)bindable.GetValue(MyThicknessProperty);
	}

	public static void SetMyThickness(BindableObject bindable, double value)
	{
		bindable.SetValue(MyThicknessProperty, value);
	}

	private static void OnMyThicknessChanged(BindableObject bindable, object oldValue, object newValue)
	{
		GaugeRangesDefinition gaugeRangesDefinition = (GaugeRangesDefinition)bindable;
		double myThickess = (double)newValue;
		gaugeRangesDefinition.StartThickness = myThickess;
	}
}
```

## See Also

- [Gauge Overview]({%slug gauge-overview%})
