---
title: Templated Rating
page_title: .NET MAUI Rating Documentation | Templated Rating
description: Check our &quot;Templated Rating&quot; documentation article for Telerik Rating for .NET MAUI.
position: 5
slug: rating-templated-rating
---

# Templated Rating

**RadTemplatedRating** component is designed to be used in the cases where it is easier to provide a template (e.g. just an image) for the rating items instead of creating custom **RadPathGeometry**. On top of the [common Rating API]({%slug rating-configuration%}) this component adds the following members:

* **ItemTemplate** (*DataTemplate*): Defines the template used in the rating item.
* **SelectedItemTemplate** (*DataTemplate*): Specifies the template used in the selected rating item.

> Set both templates - ItemTemplate and SelectedItemTemplate

![](images/rating-templates.png)

1. RadTemplatedRating definition in XAML:

```XAML
<telerikInput:RadTemplatedRating AutomationId="templatedRating" ValueChanged="RadTemplatedRating_ValueChanged">
    <telerikInput:RadTemplatedRating.ItemTemplate>
        <DataTemplate>
            <Image Source="unread.png" />
        </DataTemplate>
    </telerikInput:RadTemplatedRating.ItemTemplate>
    <telerikInput:RadTemplatedRating.SelectedItemTemplate>
        <DataTemplate>
            <Image Source="success.png" />
        </DataTemplate>
    </telerikInput:RadTemplatedRating.SelectedItemTemplate>
</telerikInput:RadTemplatedRating>
```

2. Namespace for the RadTemplatedRating

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"  
```

## See Also

- [Configuration]({% slug rating-configuration%})
- [Shape Rating]({% slug rating-shape-rating%})
