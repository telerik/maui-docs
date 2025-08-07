---
title: Creating a Bar Indicator with Color Based on Axis Size in UI for .NET MAUI
description: Learn how to create a bar indicator in UI for .NET MAUI and change its color based on axis size.
type: how-to
page_title: Changing Bar Indicator Color Based on Axis Size in UI for .NET MAUI
meta_title: Changing Bar Indicator Color Based on Axis Size in UI for .NET MAUI
slug: changing-bar-indicator-color-based-on-axis-size-dotnet-maui
tags: progressbar, ui-for-dotnet-maui, axis-size, progress-fill
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.0.1 | ProgressBar for .NET MAUI | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to create a bar indicator and dynamically change its color based on the axis size rather than the indicator size.

This knowledge base article also answers the following questions:
- How to make a bar indicator color change dynamically in UI for .NET MAUI?
- How to bind bar indicator color to axis size in UI for .NET MAUI?
- How to use LinearProgressBar as an alternative to Gauge in UI for .NET MAUI?

## Solution

To achieve the scenario, use the [LinearProgressBar](https://docs.telerik.com/devtools/maui/controls/progressbar/overview). 


**1.** Bind the slider value to the progress bar and define a color gradient for the progress fill. 

```xaml
<VerticalStackLayout Padding="10" x:Name="vsl1">
    <Label Text="{Binding Value, Source={x:Reference slider}}" />
    <Slider Value="{Binding Data, Mode=TwoWay}" x:Name="slider" Minimum="0" Maximum="10" />

    <VerticalStackLayout x:Name="vsl2" SizeChanged="vsl2_SizeChanged">
        <telerik:RadLinearProgressBar x:Name="prgsBar"
                                      Minimum="0"
                                      Maximum="10"
                                      TrackFill="Transparent"
                                      Value="{Binding Source={x:Reference slider}, Path=Value}"
                                      HeightRequest="50">
            <telerik:RadLinearProgressBar.ProgressFill>
                <LinearGradientBrush>
                    <LinearGradientBrush.GradientStops>
                        <GradientStop Offset="0.0" Color="Yellow" />
                        <GradientStop Offset="0.5" Color="Red" />
                        <GradientStop Offset="1.0" Color="Green" />
                    </LinearGradientBrush.GradientStops>
                </LinearGradientBrush>
            </telerik:RadLinearProgressBar.ProgressFill>
        </telerik:RadLinearProgressBar>
    </VerticalStackLayout>
</VerticalStackLayout>
```

**2.** Use the `SizeChanged` event to dynamically clip the axis size.

```csharp
public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();
        this.BindingContext = new ViewModel();
    }

    private void vsl2_SizeChanged(object sender, EventArgs e)
    {
        this.Dispatcher.DispatchDelayed(TimeSpan.FromMilliseconds(100), () =>
        {
            double fromThickness = 10;
            PathFigure pf = new PathFigure
            {
                StartPoint = new Point(0, this.vsl2.Height)
            };
            pf.Segments.Add(new LineSegment(new Point(this.vsl2.Width, this.vsl2.Height)));
            pf.Segments.Add(new LineSegment(new Point(this.vsl2.Width, 0)));
            pf.Segments.Add(new LineSegment(new Point(0, this.vsl2.Height - fromThickness)));
            PathGeometry pg = new PathGeometry();
            pg.Figures.Add(pf);
            this.vsl2.Clip = pg;
        });
    }
}

public class ViewModel : NotifyPropertyChangedBase
{
    private double data = 10;
    public double Data
    {
        get => this.data;
        set => this.UpdateValue(ref this.data, value);
    }
}
```

By using `RadLinearProgressBar`, the color gradient is defined independently of the indicator size and adapts based on axis dimensions.

## See Also

- [LinearProgressBar Overview](https://docs.telerik.com/devtools/maui/controls/progressbar/overview)
- [PathGeometry Class Documentation](https://learn.microsoft.com/en-us/dotnet/maui/user-interface/controls/shapes/geometries?view=net-maui-9.0)
- [SizeChanged Event in .NET MAUI](https://learn.microsoft.com/en-us/dotnet/api/microsoft.maui.controls.visualelement.sizechanged?view=net-maui-9.0)
