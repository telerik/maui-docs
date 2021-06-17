---
title: Disable a Segment
page_title: .NET MAUI SegmentedControl Documentation | Disable a Segment
description: Check our &quot;Disable a Segment&quot; documentation article for Telerik SegmentedControl for .NET MAUI control.
position: 3
slug: segmentedcontrol-features-disable-segment
---

# Disable a Segment

RadSegmentedControl allows you to disable each of its segments individually. 

To disable a segment you can use the **SetSegmentEnabled** method. The method accepts two arguments **index** that determines the index of the segment. And **isEnabled** that determines whether the item is enabled or not.

You can also check if an item is enabled via the **IsSegmentEnabled** method. The method accepts a single argument - **index**.

### Setting a text color

You can set the text color of the disabled segment through the **DisabledSegmentTextColor**.

### Example

The following example shows how to disable a segment and define a color.

```XAML
<telerikInput:RadSegmentedControl x:Name="segmentControl"
                                  DisabledSegmentTextColor="#CA5100"
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

And you can disable any segment with `SetSegmentEnabled` method:

```C#
this.segmentControl.SetSegmentEnabled(2, false);
```

#### Figure 1: Disabled segment

![SegmentedControl disable segment example](images/segmentcontrol-features-disablesegment-0.png) 

### See Also

- [Customize Segment Colors]({%slug segmentedcontrol-features-customizesegmentcolors%})