---
title: Shape Rating
page_title: .NET MAUI Rating Documentation - Shape Rating
description: Check our &quot;Shape Rating&quot; documentation article for Telerik Rating for .NET MAUI.
position: 4
slug: rating-shape-rating
---

# .NET MAUI Shape Rating

The `RadShapeRating` component is designed for the simplest scenarios where an ordinary Rating component is required. `RadShapeRating` allows easy customization of the colors and shape of the default rating item.

## Shape Types

`RadShapeRating` exposes the `ItemShape` property of type `RadPathGeometry` which is used to define the shape of the rating items.

For a simple and fast setup, the Rating includes various simple shapes that can be used for rating items out of the box. This is accomplished through the `RadGeometry` class. The `RadGeometry` class exposes static properties that return predefined shapes.

>tip For more details on `RadPath` and `RadPathGeometry`, refer to the [Path Overview article]({%slug path-overview%}).

## Geometries

The Rating supports the following geometry types:

- (Default) `Star`

 ![.NET MAUI Star Shape Rating](images/rating-star.png)

 <snippet id='rating-geometries-star' />

- `Circle`

 ![.NET MAUI Circle Shape Rating](images/rating-circle.png)

 <snippet id='rating-geometries-circle' />

- `Diamond`

 ![.NET MAUI Diamond Shape Rating](images/rating-diamond.png)

 <snippet id='rating-geometries-diamond' />

- `Heart`

 ![.NET MAUI Heart Shape Rating](images/rating-heart.png)

 <snippet id='rating-geometries-heart' />

- Custom `RadPathGeometry` shape:

 ![.NET MAUI Custom Shape Rating](images/rating-triangle.png)

 <snippet id='rating-geometries-customgeometry ' />

## Shapes Styling

You can control the visual appearance of the predefined shapes through the following styling settings:

* `ItemFill` (`Color`)&mdash;Specifies the color used to fill the rating item.
* `ItemStroke` (`Color`)&mdash;Defines the color used by the border around the geometry.
* `ItemStrokeThickness` (`double`)&mdash;Sets the width of the border around the geometry.
* `SelectedItemFill` (`Color`)&mdash;Defines the color used to fill the selected rating item.
* `SelectedItemStroke` (`Color`)&mdash;Sets the color used by the border around the selected geometry.
* `SelectedItemStrokeThickness` (`double`)&mdash;Specifies the width of the border around the selected geometry.

![.NET MAUI Rating Styling](images/rating-styles.png)

The following example shows how to set the shapes styling.

Define the `RadShapeRating`:

<snippet id='rating-geometries-styling' />

The following image shows the end result.

![.NET MAUI Rating Styling](images/rating-styles.png)

## See Also

- [Configuration of the Rating]({% slug rating-configuration%})
- [Templated Rating]({% slug rating-templated-rating%})
