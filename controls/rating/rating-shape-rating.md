---
title: Shape Rating
page_title: .NET MAUI Rating Documentation | Shape Rating
description: Check our &quot;Shape Rating&quot; documentation article for Telerik Rating for .NET MAUI.
position: 4
slug: rating-shape-rating
---

# Shape Rating

The `RadShapeRating` component is designed for the simplest scenarios where an ordinary Rating component is required. `RadShapeRating` allows easy customization of the colors and shape of the default rating item.

## Shape Types

`RadShapeRating` exposes the `ItemShape` property of type `RadPathGeometry` which is used to define the shape of the rating items.

For an easy and fast setup, the Rating includes several simple shapes that can be used for rating items out of the box. This is accomplished through the static `Geometries`. The `Geometries` class exposes static properties that return predefined shapes.

>tip For more details on `RadPath` and `RadPathGeometry`, refer to the [Path Overview article]({%slug path-overview%}).

## Geometries

The Rating supports the following geometry types:

- (Default) `Star`

 ![Star Shape Rating](images/rating-star.png)

 ```XAML
<telerikInput:RadShapeRating AutomationId="defaultRating" />
 ```

- `Circle`

 ![Circle Shape Rating](images/rating-circle.png)

 ```XAML
<telerikInput:RadShapeRating ItemShape="{x:Static telerikInput:Geometries.Circle}" AutomationId="circleRating" />
 ```

- `Diamond`

 ![Diamond Shape Rating](images/rating-diamond.png)

 ```XAML
<telerikInput:RadShapeRating ItemShape="{x:Static telerikInput:Geometries.Diamond}" AutomationId="diamondRating" />
 ```

- `Heart`

 ![](images/rating-heart.png)

 ```XAML
<telerikInput:RadShapeRating ItemShape="{x:Static telerikInput:Geometries.Heart}" AutomationId="heartRating" />
 ```

- Custom `RadPathGeometry` shape:

 ![](images/rating-triangle.png)

 ```XAML
 <telerikInput:RadShapeRating AutomationId="triangularRating">
    <telerikInput:RadShapeRating.ItemShape>
        <telerikCommon:RadPathGeometry>
            <telerikCommon:RadPathFigure StartPoint="0, 1">
                <telerikCommon:RadLineSegment Point="1, 1" />
                <telerikCommon:RadLineSegment Point="0.5, 0" />
                <telerikCommon:RadLineSegment Point="0, 1" />
            </telerikCommon:RadPathFigure>
        </telerikCommon:RadPathGeometry>
    </telerikInput:RadShapeRating.ItemShape>
</telerikInput:RadShapeRating>
 ```

 In the example, the `telerikCommon` namespace is defined like this:

 ```XAML
xmlns:telerikCommon="clr-namespace:Telerik.XamarinForms.Common;assembly=Telerik.Maui.Controls.Compatibility"
 ```

## Shapes Styling

You can control the visual appearance of the predefined shapes through the following styling settings:

* `ItemFill` (`Color`)&mdash;Specifies the color used to fill the rating item.
* `ItemStroke` (`Color`)&mdash;Defines the color used by the border around the geometry.
* `ItemStrokeThickness` (`double`)&mdash;Sets the width of the border around the geometry.
* `SelectedItemFill` (`Color`)&mdash;Defines the color used to fill the selected rating item.
* `SelectedItemStroke` (`Color`)&mdash;Sets the color used by the border around the selected geometry.
* `SelectedItemStrokeThickness` (`double`)&mdash;Specifies the width of the border around the selected geometry.

![Rating Styling](images/rating-styles.png)

### Example

Define the `RadShapeRating`:

```XAML
<telerikInput:RadShapeRating AutomationId="styledRating"
                          ItemFill="YellowGreen"
                          ItemStroke="YellowGreen"
                          SelectedItemFill="Pink"
                          SelectedItemStroke="Red" />
```

Add the namespace:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"  
```


The following image shows the end result.

 ![Rating Styling](images/rating-styles.png)

## See Also

- [Configuration of the Rating]({% slug rating-configuration%})
- [Templated Rating]({% slug rating-templated-rating%})
