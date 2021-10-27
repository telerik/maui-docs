---
title: Configuration
page_title: .NET MAUI Rating Documentation | Configuration
description: Check our &quot;Configuration&quot; documentation article for Telerik Rating for .NET MAUI.
position: 2
slug: rating-configuration
---

# Configuration

RadRating is presented by two components named [RadShapeRating]({% slug rating-shape-rating%}) and [RadTemplatedRating]({% slug rating-templated-rating%}) in order to provide various visualizations of the rating functionality. 

The features described in this article are common for both `RadShapeRating` and `RadTemplatedRating`.

>tip RadShapeRating and RadTemplatedRating inherit from the `RatingBase` abstract class that provides their common features.

## Rating Value

RadRating exposes a `Value` property that is used to set and read the number of the selected rating items.

```XAMl
<telerikInput:RadShapeRating AutomationId="radRating"
                             Value="4" />
```

And the namespace:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

## Configuration Settings

* `ItemsCount`: Defines the number of the items that are visualized in the rating control. The default value is `5` items;
* `ItemsSpacing`: Specifies the distance between the separate items in pixels. Default value is `10px`;

```XAML
<telerikInput:RadShapeRating AutomationId="radRating"
                             Value="4"
                             ItemsCount="7"
                             ItemsSpacing="20" />
```

And the namespace:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

## See Also

- [RadShapeRating]({% slug rating-shape-rating%})
- [RadTemplatedRating]({% slug rating-templated-rating%})