---
title: Styling
page_title: .NET MAUI Path Documentation | Styling
description: Check our &quot;Styling&quot; documentation article for Telerik Path for .NET MAUI.
position: 8
previous_url: /controls/path/path-styling
slug: path-styling
---

# Styling

The `RadPath` element exposes the following properties you can use to customize the look of the path figures:

* `Fill`: Used for setting up the color within the figures. You have to set an object of type `RadBrush`. This can be a `RadSolidColorBrush` or a `RadSweepGradientBrush`
* `Stroke`: You can use this property to set the stroke color.
* `StrokeThickness`: You can use this property to set the thickness of the stroke.
* `BackgroundColor`: You can use this property to modify the color of the rectangle which contains the specific figure.

## Styling the Path using the RadSweepGradientBrush

Define the control.

```XAML
<telerikPrimitives:RadPath x:Name="gradientPath"
                            StrokeThickness="1"
                            Stroke="White"
                            Geometry="{x:Static telerikInput:Geometries.Diamond}">
    <telerikPrimitives:RadPath.Fill>
        <telerikCommon:RadSweepGradientBrush>
            <x:Arguments>
                <Point>0.5, 0.5</Point>
            </x:Arguments>
            <telerikCommon:RadSweepGradientStop>
                <x:Arguments>
                    <Color>#1481FF</Color>
                    <x:Double>180</x:Double>
                </x:Arguments>
            </telerikCommon:RadSweepGradientStop>
            <telerikCommon:RadSweepGradientStop>
                <x:Arguments>
                    <Color>#BCE1FF</Color>
                    <x:Double>360</x:Double>
                </x:Arguments>
            </telerikCommon:RadSweepGradientStop>
        </telerikCommon:RadSweepGradientBrush>
    </telerikPrimitives:RadPath.Fill>
</telerikPrimitives:RadPath>
```

Add the namespaces:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
xmlns:telerikPrimitives="clr-namespace:Telerik.XamarinForms.Primitives;assembly=Telerik.Maui.Controls.Compatibility"
xmlns:telerikCommon="clr-namespace:Telerik.XamarinForms.Common;assembly=Telerik.Maui.Controls.Compatibility"           
```

## Styling the Path using the RadSolidColorBrush

Define the control.

```XAML
<telerikPrimitives:RadPath x:Name="solidPath"
                            Grid.Row="0"
                            StrokeThickness="2"
                            Stroke="#1481FF"
                            Fill="#BCE1FF">
    <telerikPrimitives:RadPath.Geometry>
        <telerikCommon:RadPathGeometry>
            <telerikCommon:RadPathFigure StartPoint="0, 1">
                <telerikCommon:RadLineSegment Point="1, 1" />
                <telerikCommon:RadLineSegment Point="0.5, 0" />
                <telerikCommon:RadLineSegment Point="0, 1" />
            </telerikCommon:RadPathFigure>
        </telerikCommon:RadPathGeometry>
    </telerikPrimitives:RadPath.Geometry>
</telerikPrimitives:RadPath>
```

Add the used namespace:

```XAML
xmlns:telerikPrimitives="clr-namespace:Telerik.XamarinForms.Primitives;assembly=Telerik.Maui.Controls.Compatibility"
xmlns:telerikCommon="clr-namespace:Telerik.XamarinForms.Common;assembly=Telerik.Maui.Controls.Compatibility"           
```


The following image shows the result:

![RadPath Styling](images/path_styling.png)


## See Also

- [PathGeometry]({% slug path-structure %})
