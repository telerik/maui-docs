---
title: Docking Functionality
page_title: .NET MAUI DockLayout Documentation - Docking Functionality
description: "Learn how to use the docking functionality and position child elements with the Telerik UI for .NET MAUI DockLayout control."
position: 2
previous_url: /controls/docklayout/docklayout-docking
slug: docklayout-docking
---

# .NET MAUI Docking Functionality for DocjkLayout control

The DockLayout provides options for setting the position of child elements to different areas of the layout and aligning multiple elements to one side.  

## Setting the Position of Child Elements

To define the docking side of a child element inside the dock layout component, use **RadDockLayout.Dock** attached property which receives any of the following values:

* `Left`
* `Top`
* `Right`
* `Bottom`

The way the child elements are docked and arranged depends on their order inside the DockLayout’s Children collection (the order they’re defined in XAML).

The following example demonstrates how to utilize the docking functionality:

```XAML
<telerik:RadDockLayout x:Name="dockLayout">
    <Label Text="Left" telerik:RadDockLayout.Dock="Left" WidthRequest="60" BackgroundColor="LightPink" />
    <Label Text="Top" telerik:RadDockLayout.Dock="Top" HeightRequest="60" BackgroundColor="LightGreen" />
    <Label Text="Right" telerik:RadDockLayout.Dock="Right" WidthRequest="60" BackgroundColor="LightBlue" />
    <Label Text="Bottom" telerik:RadDockLayout.Dock="Bottom" BackgroundColor="LightYellow" />
</telerik:RadDockLayout>
```

Define `telerik` namespace in the following way:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```


The following image shows the result on different platforms:

![DockLayout Docking](images/docklayout_docking_feature.png)

## Positioning Multiple Elements on One Side

Setting the same docking side to a few child elements will arrange them according to their order inside the DockLayout children collection.  

```XAML
<telerik:RadDockLayout x:Name="dockLayout" >
    <Label Text="Left 1" telerik:RadDockLayout.Dock="Left" WidthRequest="60" BackgroundColor="LightPink" />
    <Label Text="Left 2" telerik:RadDockLayout.Dock="Left" WidthRequest="60" BackgroundColor="LightGreen" />
    <Label Text="Left 3" telerik:RadDockLayout.Dock="Left" WidthRequest="60" BackgroundColor="LightBlue" />
    <Label Text="Last Child" telerik:RadDockLayout.Dock="Left" BackgroundColor="LightYellow" />
</telerik:RadDockLayout>
```


The following image shows the end result.

![DockLayout Elements on one side](images/docklayout_positiononeside.png)

## Setting the Position of the Last Child Element

By default, the last element inside the DockLayout stretches over the remaining space that is not occupied by the other child elements.

You can prevent this behavior by setting `StretchLastChild` property of the DockLayout control to `False` as demonstrated in the following example.

```XAML
<telerik:RadDockLayout x:Name="dockLayout" StretchLastChild="False">
    <Label Text="Left" telerik:RadDockLayout.Dock="Left" WidthRequest="60" BackgroundColor="LightPink" />
    <Label Text="Top" telerik:RadDockLayout.Dock="Top" HeightRequest="60" BackgroundColor="LightGreen" />
    <Label Text="Right" telerik:RadDockLayout.Dock="Right" WidthRequest="60" BackgroundColor="LightBlue" />
    <Label Text="Bottom" telerik:RadDockLayout.Dock="Bottom" BackgroundColor="LightYellow" />
</telerik:RadDockLayout>
```

The following image shows the end result.

![DockLayout Positioning](images/docklayout_positionlast.png)
