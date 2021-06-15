---
title: Customize Segment Colors
page_title: .NET MAUI SegmentedControl Documentation | Customize Segment Colors
description: Check our &quot;Customize Segment Colors&quot; documentation article for Telerik SegmentedControl for .NET MAUI control.
position: 4
slug: segmentedcontrol-features-customizesegmentcolors
---

# Customize Segment Colors

**RadSegmentedControl** has several properties which you can use to customize the text and background colors of the segments.

### List of color properties

There are different colors applied to the segments in their different states. The control exposes the following **properties**:

- **SegmentBackgroundColor**: This is the background color applied to the unselected segments.
- **SegmentTextColor**: This is the text color applied to the unselected segments.

- **SelectedSegmentBackgroundColor**: This is the background color applied to the selected segment.
- **SelectedSegmentTextColor**: This is the text color applied to the selected segment.

- **DisabledSegmentTextColor**: This is the text color applied to the disabled segments.

### Example

This example shows setting the different segment colors.

```XAML
<telerikInput:RadSegmentedControl x:Name="segmentControl"
                                  Margin="10"
                                  DisabledSegmentTextColor="#C2C3C9"
                                  HeightRequest="60"
                                  SegmentBackgroundColor="#FFFFFF"
                                  SegmentTextColor="#3A9BFD"
                                  SelectedSegmentBackgroundColor="#3A9BFD"
                                  SelectedSegmentTextColor="#FFFFFF"
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

#### Figure 1: Customized segment colors
 
![SegmentedControl colors customization](images/segmentcontrol-features-customizecolors-0.png) 

### See Also

- [Getting Started]({%slug segmentedcontrol-getting-started%})
- [Selection]({%slug segmentedcontrol-features-selection%})
- [Disable segment]({%slug segmentedcontrol-features-disable-segment%})