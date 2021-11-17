---
title: Geometry Types
page_title: .NET MAUI Path Documentation | Geometry Types
description: "Use the predefined geometry types the Telerik Path for .NET MAUI supports and create your custom shapes for the control to visualize."
position: 3
slug: geometry-types
---

# Geometry Types

The Path provides a set of preconfigured geometry types and enables you to set custom geometries as well.

## Built-In Geometries

The available built-in geometry types are included in the `Telerik.XamarinForms.Input.Geometries` static class.

The supported preconfigured geometries are:

* Star
* Circle
* Heart
* Diamond

....example

## Custom Geometries

You can also create a custom geometry, which will be visualized by the Path. For that purpose, create an object of type `RadPathGeometry` and add a `RadPathFigure` with the needed segments.

The following example shows a Path with an Arc definition:

```XAML
<telerikPrimitives:RadPath x:Name="customPath"
                       Grid.Row="0"
                       StrokeThickness="4"
                       Stroke="#2EC262">
    <telerikCommon:RadPathGeometry>
        <telerikCommon:RadPathFigure StartPoint="0.85, 0.85">
            <telerikCommon:RadArcSegment Center = "0.5, 0.5"
                                         Size = "1, 1"
                                         StartAngle = "315"
                                         SweepAngle = "270" />
        </telerikCommon:RadPathFigure>
    </telerikCommon:RadPathGeometry>
</telerikPrimitives:RadPath>
```

Add the following namespace:

```XAML
xmlns:telerikPrimitives="clr-namespace:Telerik.XamarinForms.Primitives;assembly=Telerik.Maui.Controls.Compatibility"
xmlns:telerikCommon="clr-namespace:Telerik.XamarinForms.Common;assembly=Telerik.Maui.Controls.Compatibility"
```

The following image shows the end result.

![RadPath Figures](images/custom_default_paths.png)

## See Also

- [MultiPath]({% slug path-multipath %})
- [Styling]({% slug path-styling %})
