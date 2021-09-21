---
title: Docking functionality
page_title: .NET MAUI DockLayout Documentation | Docking functionality
description: Check our &quot;Key Features&quot; documentation article for Telerik DockLayout for .NET MAUI control.
position: 2
slug: docklayout-docking
---

# Docking functionality

To define the docking side of a child element inside the dock layout component, use **RadDockLayout.Dock** attached property which receives any of the following values:

* Left
* Top
* Right
* Bottom

The way the child elements are docked and arranged depends on their order inside the DockLayout’s Children collection (the order they’re defined in XAML).

Following is a quick example on how you could utilize the docking functionality:

<snippet id='docklayout-docking-feature' />
```XAML
<telerik:RadDockLayout x:Name="dockLayout">
    <Label Text="Left" telerik:RadDockLayout.Dock="Left" WidthRequest="60" BackgroundColor="LightPink" />
    <Label Text="Top" telerik:RadDockLayout.Dock="Top" HeightRequest="60" BackgroundColor="LightGreen" />
    <Label Text="Right" telerik:RadDockLayout.Dock="Right" WidthRequest="60" BackgroundColor="LightBlue" />
    <Label Text="Bottom" telerik:RadDockLayout.Dock="Bottom" BackgroundColor="LightYellow" />
</telerik:RadDockLayout>
```

where *telerik* is defined like this:

```XAML
xmlns:telerik="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
```

Check the result on different platforms below:

![RadDockLayout Docking](images/docklayout_docking_feature.png)

## Dock multiple elements on one side

Setting the same docking side to a few child elements will arrange them according to their order inside the DockLayout’s Children collection.  

<snippet id='docklayout-position-elementsoneside'/>
```XAML
<telerik:RadDockLayout x:Name="dockLayout" >
    <Label Text="Left 1" telerik:RadDockLayout.Dock="Left" WidthRequest="60" BackgroundColor="LightPink" />
    <Label Text="Left 2" telerik:RadDockLayout.Dock="Left" WidthRequest="60" BackgroundColor="LightGreen" />
    <Label Text="Left 3" telerik:RadDockLayout.Dock="Left" WidthRequest="60" BackgroundColor="LightBlue" />
    <Label Text="Last Child" telerik:RadDockLayout.Dock="Left" BackgroundColor="LightYellow" />
</telerik:RadDockLayout>
```

And the result is:

![RadDockLayout Elements on one side](images/docklayout_positiononeside.png)

## Configure last child element position

By default, the last element inside the DockLayout stretches along the remaining space not occupied by the other child elements. You can prevent this behavior by setting **StretchLastChild** property of the DockLayout control to *False*. Check the example below how it would work when set to *False*:

<snippet id='docklayout-position-lastelement'/>
```XAML
<telerik:RadDockLayout x:Name="dockLayout" StretchLastChild="False">
    <Label Text="Left" telerik:RadDockLayout.Dock="Left" WidthRequest="60" BackgroundColor="LightPink" />
    <Label Text="Top" telerik:RadDockLayout.Dock="Top" HeightRequest="60" BackgroundColor="LightGreen" />
    <Label Text="Right" telerik:RadDockLayout.Dock="Right" WidthRequest="60" BackgroundColor="LightBlue" />
    <Label Text="Bottom" telerik:RadDockLayout.Dock="Bottom" BackgroundColor="LightYellow" />
</telerik:RadDockLayout>
```

And here is how it looks:

![RadDockLayout Positioning](images/docklayout_positionlast.png)

## See Also

- [Getting Started]({% slug docklayout-getting-started%})
