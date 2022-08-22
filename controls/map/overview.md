---
title: Overview
page_title: .NET MAUI Map Documentation - Overview
description: Check our &quot;Overview&quot; documentation article for Telerik Map for .NET MAUI.
position: 0
slug: map-overview
---

# Overview

**Telerik Map for .NET MAUI** is a data visualization control whose primary purpose is to visualize rich spatial data. The control provides visualization of ESRI shapefiles that consist of geometric objects, such as lines, polylines and polygons. Such objects are commonly used to display various schemes, for example floor plans and seats distribution, all the way to parts of maps for countries, roads, rivers, etc.

![Map Overview](images/map_overview.png)

## Key Features

* [Shapefile visualization]({% slug map-layers-overview %})&mdash;The Map can display rich spatial data from ESRI shapefiles. Each shapefile should be loaded and configured through a ShapefileLayer instance added to the Layers collection of the control.

* [Support for multiple layers]({% slug map-layers-overview %})&mdash;The layered architecture of the control provides the option to load multiple shapefiles, so you can visualize different types of elements on the same map.

* [Various ways to load shapefiles]({% slug map-layers-shapefilelayer %})&mdash;You can load the shapefiles from a stream, from a file added as embedded resource or a file located on the device,etc.

* [Pan and Zoom]({% slug map-pan-zoom %})&mdash;The Map provides pan and zoom functionality that will help you interact with the view and inspect your data. You could choose between only pan, only zoom or both through `InteractionMode` property. 

* [Shape Labels]({% slug map-layers-shapefilelayer %}#labels)&mdash;You can show a label for each shape in the Map control through the `LabelAttributeName` property of the ShapefileLayer instance.

* [Selection]({% slug map-selection %})&mdash;The control supports single and multiple selection of shapes to help you draw attention on specific areas. 

* [Commands]({% slug map-commands %})&mdash;The Map allows you to replace the default behavior of `ZoomIn` and `ZoomOut` commands with a custom implementation.
 
* [Shapes Styling]({% slug map-styling-shapesstyles %})&mdash;You can apply various Fill and Stroke colors to the shapes to make the map consistent with the design of your app. 

## Next Steps

- [Getting Started with Telerik UI for .NET MAUI Map]({%slug map-getting-started %})


## See Also

- [.NET MAUI Map product page](https://www.telerik.com/maui-ui/map)
- [.NET MAUI Map forum page](https://www.telerik.com/forums/maui?tagId=1870)
- [Telerik .NET MAUI blogs](https://www.telerik.com/blogs/tag/.net-maui)
- [Telerik .NET MAUI roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
