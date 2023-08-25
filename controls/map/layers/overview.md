---
title: Layers Overview
page_title: .NET MAUI Map Documentation - Map Layers Overview
description: Learn more about the Map Layers used in Telerik UI for .NET MAUI Map control.
position: 0
slug: map-layers-overview
---

# .NET MAUI Map Layers

The Map control visualizes spatial data using **layered architecture**. It can display spatial data points
(location of cities), polylines (road connections), or polygons (shape of countries or continents) in a **geographic coordinate system**. In this coordinate system, a point on the surface of the earth is defined using latitudes and longitudes.

* **Latitude**&mdash;This is measured as the angle from the equatorial plane to the line drawn from the center of the earth to the point on the surface. Usually latitude values range from 90° (toward the North Pole and suffixed with "N") to -90° (towards the South Pole and suffixed with "S").
* **Longitude**&mdash;This is measured on the equatorial plane and is defined as the angle between the line drawn from the center of the earth to the point and the line drawn from center of the earth to the prime meridian. Usually the longitude values range from 180° (to the east of prime meridian and suffixed with "E") to -180° (to the west of prime meridian and suffixed with "W").

![.NET MAUI Map-Geographic Coordinate System](../images/map-geographiccoordinatesystem.png)

The position of the spatial data is described by the `Location` structure, that has the following properties:

* `Latitude` (double): Gets the latitude value of the location. The value have to be between -90° and 90°.
* `Longitude` (double): Gets the longitude value of the location. The value have to be between -180° and 180°.

The Map control works with layers of type `ShapefileLayer` that use ESRI shapefiles as a data source. For detailed information on how shapefiles can be utilized go to [ShapefileLayer]({% slug map-layers-shapefilelayer%}) topic.

## See Also

- [ShapefileLayer]({% slug map-layers-shapefilelayer%})
