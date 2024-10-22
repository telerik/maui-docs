---
title: Labels Styling
page_title: .NET MAUI Map Documentation - Labels Styling
description: Learn how to style the labels in the Telerik UI for .NET MAUI Map control.
position: 0
slug: map-styling-labelstyles
---

# .NET MAUI Map Label Styling

The `MapShapefileLayer` has a `ShapeLabelStyle` property that is of `MapShapeLabelStyle` type and defines the style of the labels.

`MapShapeLabelStyle` provides the following properties you can use to customize the way labels on the map will look:

* `TextColor`
* `FontSize`
* `FontFamily`
* `FontAttributes`

The example shows the `ShapeLabelStyle` property applied:

<snippet id='map-styling-shapelabelstyle' />

where the `Source` and the `DataSource` of the `MapShapeReader` have to be set to a `.shp` and `.dbf` files, respectively:

<snippet id='map-interactionmode-settintsource' />

And the used namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

Here is the result:

![.NET MAUI Map Labels Styling](../images/map_styling_labelsstyle.png)

## See Also

- [ShapefileLayer]({% slug map-layers-shapefilelayer%})
- [Shapes Styling]({% slug map-styling-shapesstyles%})
