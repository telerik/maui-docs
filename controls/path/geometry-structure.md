---
title: PathGeometry
page_title: .NET MAUI Path Documentation | PathGeometry
description: Check our &quot;PathGeometry&quot; documentation article for Telerik Path for .NET MAUI.
position: 2
slug: path-structure
---

# PathGeometry

To create a specific Path, you need to set a `RadPathGeometry` object to its `Geometry` property. The `RadPathGeometry` object exposes a `Figures` property which is a collection of `RadPathFigures`.

## RadPathFigure

Each of the `RadPathFigure` objects is composed of one or several segments. These can be a `RadArcSegment` or a `RadLineSegment`. Adding several segments in combination with setting up the `StartPoint` of the `RadPathFigure` is enough for you to create the desired figure which have to be added to the figures collection of the geometry.

Each line or arc segment you add to the path figure is drawn consequently - its starting point is the last point of the previous segment of the Segments collection of the `PathFigure` object. The first segment uses the `StartPoint` of the path figure as a starting point.

### RadArcSegment

The `RadArcSegment` represents an elliptical arc between two points. It exposes the following properties:

* `Center`: Defines the center point of the arc.
* `Size`: Sets the x- and y-diameter of the arc as a Size structure.
* `StartAngle`: Determines the angle from which the arc segment will start.
* `SweepAngle`: Specifies the length in degrees from the first to the second arc point. Positive angles are counter clockwise and negative angles clockwise.

The scheme below shows how `StartAngle` and `SweepAngle` are applied to the `ArcSegment`:

![ArcSegment Angles](images/path_arcsegment_scheme.png)

The following example shows a sample implementation of an `RadArcSegment` object.

Define the Path.

<snippet id='path-geometry-simplearc-xaml' />

Add the namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

### RadLineSegment

The `RadLineSegment` creates a line between two points in a `RadPathFigure`. The starting point of the line is defined either by the previous segment's end point or by the `StartPoint` of the `PathFigure` object. The end point is defined by the `Point` property of the `LineSegment` object.

The thickness and the color of the line are determined by the `StrokeThickness` and `Stroke` properties of the Path object to which this line figure is added.

The following example shows how to create a line `PathFigure`.

Define the Path.

<snippet id='path-geometry-simpleline-xaml' />

Add the namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

## Example

The following example shows how to create a more complex `RadPathGeometry` object and add a line with curved edges to its Figures collection.

1. First, define the `RadPath` figure:

  <snippet id='path-geometry-customline-xaml' />

1. Add the namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

1. Then, set its `Geometry` to have the following structure:

 <snippet id='path-geometry-customline-segment' />

1. Add the namespace:

 ```C#
using Microsoft.Maui.Graphics;
using Telerik.XamarinForms.Common;
 ```

The following image shows the result after creating the three Paths:

![Path Geometry](images/path_geometry.png)

## See Also

- [MultiPath]({% slug path-multipath %})
- [Styling]({% slug path-styling %})
