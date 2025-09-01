---
title: Getting Started
page_title: NET MAUI Map Documentation - Getting Started
description: Get started with the Telerik UI for .NET MAUI Map and add the control to your .NET MAUI project.
position: 1
slug: map-getting-started
---

# Getting Started with the .NET MAUI Map

This guide provides the information you need to start using the Telerik UI for .NET MAUI Map by adding the control to your project.

At the end, you will achieve the following result.

![.NET MAUI Map Getting Started](images/map_getting_started.png)

## Prerequisites

Before adding the Map, you need to:

1. [Set up your .NET MAUI application]({%slug maui-getting-started %}#step-1-set-up-your-net-maui-application).

1. [Download Telerik UI for .NET MAUI]({% slug maui-getting-started %}#step-2-download-telerik-ui-for-net-maui).

1. [Install Telerik UI for .NET MAUI]({%slug maui-getting-started %}#step-3-install-telerik-ui-for-net-maui).

>important The Map is rendered through the [SkiaSharp graphics library](https://skia.org/).

## Define the Control

1. When your .NET MAUI application is set up, you are ready to add a Map control to your page.

 <snippet id='map-getting-started-xaml' />

1. Add the following namespace:

 ```XAML
 xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

1. `RadMap` uses `.shp` files that contain the coordinates of the shapes that will be drawn by the map and an optional `.dbf` file for each `.shp` file with additional attributes of the shapes.

 You need to assign the `.shp` file containing the data through the `Source` property of the `MapShapeReader` like this:

 <snippet id='map-gettingstarted-setting-source' />

>note In the example the `.shp` file is loaded as an `EmbeddedResource`, other options can be used as well, please check them in the [ShapefileLayer]({%slug map-layers-shapefilelayer%}) topic.

## Additional Resources

- [.NET MAUI Map Product Page](https://www.telerik.com/maui-ui/map)
- [.NET MAUI Map Forum Page](https://www.telerik.com/forums/maui?tagId=1870)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)

## See Also

- [ShapefileLayer]({% slug map-layers-shapefilelayer%})
- [Selection]({% slug map-selection%})
- [Styling]({% slug map-styling-shapesstyles %})

