---
title: Commands
page_title: .NET MAUI Map Documentation - Map Commands
description: Learn how to use the exposed commands for handling the zoom level in the Telerik UI for .NET MAUI Map control.
position: 8
slug: map-commands
---

# .NET MAUI Map Commands

The Telerik UI for .NET MAUI Map control provides the following commands of type `ICommand` which handle the zoom level of the visualized shapes:

* `ZoomInCommand`

* `ZoomOutCommand`

You can manually call these commands, for example on button click action, to zoom-in or zoom-out respectively, the shapes displayed in `RadMap`.

Following is a quick example on how the commands of the Map control can be called from external UI:

1. The `RadMap` definition:

 <snippet id='map-zoom-level-xaml' />

1. Where the `Source` of the `MapShapeReade`r is defined like this:

 <snippet id='map-interactionmode-settintsource' />

1. Add two buttons that will execute the Map commands - their `Command` property is bound to the corresponding Zoom command of the Map instance:

 ```XAML
<Button Text="Zoom In" Command="{Binding Source={x:Reference map}, Path=ZoomInCommand}"/>
<Button Text="Zoom Out" Command="{Binding Source={x:Reference map}, Path=ZoomOutCommand}"/>
 ```

1. And the namespace for `RadMap`: 

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

## See Also

- [Selection]({%slug map-selection%})