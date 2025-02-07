---
title: Geometry Types
page_title: .NET MAUI Path Documentation - Geometry Types
description: Use the predefined geometry types the Telerik Path for .NET MAUI supports and create your custom shapes for the control to visualize.
position: 3
slug: geometry-types
---

# .NET MAUI Path Geometry Types

The Path provides a set of preconfigured geometry types and enables you to set custom geometries as well.

## Built-In Geometries

The available built-in geometry types are included in the `Telerik.Maui.Controls.Paths.RadGeometry` class.

The supported preconfigured geometries are:

* Star
* Circle
* Heart
* Diamond

## Custom Geometries

You can also create a custom geometry, which will be visualized by the Path. For that purpose, create an object of type `RadPathGeometry` and add a `RadPathFigure` with the needed segments.

The following example shows a Path with an Arc definition:

```XAML
<telerik:RadPath x:Name="customPath"
                       StrokeThickness="4"
                       Stroke="#2EC262">
    <telerik:RadPath.Geometry>
        <telerik:RadPathGeometry>
            <telerik:RadPathFigure StartPoint="0.85, 0.85">
                <telerik:RadArcSegment Center="0.5, 0.5"
                                             Size="1, 1"
                                             StartAngle="315"
                                             SweepAngle="270" />
            </telerik:RadPathFigure>
        </telerik:RadPathGeometry>
    </telerik:RadPath.Geometry>
</telerik:RadPath>
```

Add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```


The following image shows the end result.

![.NET MAUI Path Figures](images/custom_default_paths.png)

## See Also

- [MultiPath]({% slug path-multipath %})
- [Styling]({% slug path-styling %})
