---
title: Getting Started
page_title: Getting Started with .NET MAUI Path Control
description: Check our &quot;Getting Started&quot; documentation article for Telerik Path for .NET MAUI.
position: 1
slug: path-getting-started
---

# Getting Started

>important RadPath is rendered via the **SkiaSharp** graphics library so you need to install also `SkiaSharp.Views.Forms.Maui.Controls.Compatibility`.

## Define RadPath control

RadPath control exposes **Geometry** property which should be assigned to a RadPathGeometry object. [RadPathGeometry]({% slug path-structure %}) consists of different RadPathFigures such as line and arc. RadPath also provides a few predefined geometries such as star, circle and other. Below you can find two examples of creating a path with built-in as well as custom geometry.

## Creating RadPath with built-in geometry

RadPath provides several built-in geometries that can be found in the *Telerik.XamarinForms.Input.Geometries* static class. Below you could find a list of the available geometries:

* Star;
* Circle;
* Heart;
* Diamond.

You can choose any of those and set it directly to the Geometry property of the Path component:

```XAML
<telerikPrimitives:RadPath x:Name="starPath"
                           StrokeThickness="0" 
                           Fill="#FFC325"
                           Geometry="{x:Static telerikInput:Geometries.Star}" />
```

In addition to this you need to add the following namespaces:

```XAML

```

Register a SkiaSharp renderer inside the `Configure` method of the **Startup.cs** file of your project:

```C#
.UseSkiaSharpCompatibilityRenderers()
.UseSkiaSharpHandlers()    
```

Add the following usings inside the `Startup.cs` file:

```C#
using SkiaSharp.Views.Maui.Controls.Compatibility;
using SkiaSharp.Views.Maui.Controls;
```

## Creating RadPath with custom geometry

You are free to create a custom geometry which will be visualized by the **RadPath** control. For that purpose, you need to create object of type **RadPathGeometry** and add a **RadPathFigure** with the needed segments.

The next example shows a RadPath with an Arc definition:

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

and add the following namespace:

```XAML

```

Both RadPath objects appearance can be reviewed in the image below:

![RadPath Figures](images/custom_default_paths.png)

## See Also

- [PathGeometry]({% slug path-structure %})
