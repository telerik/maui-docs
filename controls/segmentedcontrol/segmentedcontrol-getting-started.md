---
title: Getting Started
page_title: Getting Started with .NET MAUI SegmentedControl Control
description: Check our &quot;Getting Started&quot; documentation article for Telerik SegmentedControl for .NET MAUI control.
position: 1
slug: segmentedcontrol-getting-started
---

# Getting Started

## Define SegmentedControl

Add RadSegmentedControl definition in XAML:

```XAML
<telerikInput:RadSegmentedControl x:Name="segmentControlText"
								  HeightRequest="60"
                                  VerticalOptions="Start">
    <telerikInput:RadSegmentedControl.ItemsSource>
        <x:Array Type="{x:Type x:String}">
            <x:String>Popular</x:String>
            <x:String>Library</x:String>
            <x:String>Playlists</x:String>
            <x:String>Friends</x:String>
        </x:Array>
    </telerikInput:RadSegmentedControl.ItemsSource>
</telerikInput:RadSegmentedControl>
```

Add the following namespace:

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Compatibility"
```

Register a renderer inside the `ConfigureMauiHandlers` method of the **Startup.cs** file of your project:

```C#
.ConfigureMauiHandlers(handlers => {
			
	// renderer for Telerik UI for MAUI SegmentedControl
	handlers.AddCompatibilityRenderer(typeof(Telerik.XamarinForms.Input.RadSegmentedControl), typeof(InputRenderer.SegmentedControlRenderer));
	.....			
```

## Set segment colors

You can set the background of the segments via the **SegmentBackgroundColor** property. The color will be applied to all segments except the selected one. To change the background of the selected item you can set the **SelectedSegmentBackgroundColor**

To set the text color of the strings in the items via the **SegmentTextColor** property. The color of the selected segment can be set via the **SelectedSegmentTextColor** property.

You can find an example with the selected color properties in the [Selection]({%slug segmentedcontrol-features-selection%}) article.


### See Also

- [Selection]({%slug segmentedcontrol-features-selection%})
- [Disable segment]({%slug segmentedcontrol-features-disable-segment%})
