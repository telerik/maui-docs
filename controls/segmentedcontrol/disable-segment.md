---
title: Disabled Segments
page_title: .NET MAUI SegmentedControl Documentation - Disabled Segments
description: Learn more about how to disable individual segments in the Telerik UI for .NET MAUI SegmentedControl.
position: 7
slug: segmentedcontrol-disable-segment
---

# Disabling Segments in .NET MAUI SegmentedControl

The SegmentedControl allows you to disable each of its segments individually. A disabled segment does not respond to user interaction and is excluded from the selection.

The control exposes the following methods for managing the enabled state of a segment:

* `SetSegmentEnabled(int index, bool isEnabled)`&mdash;Sets the enabled state of the segment at the specified `index`. The method can be called before the control is loaded; the pending state is applied once the control is attached to the visual tree.
* `IsSegmentEnabled(int index)`&mdash;Returns the current enabled state of the segment at the specified `index`.

## Example

The following example shows how to disable a segment.

**1.** Define the SegmentedControl:

<snippet id='segmentcontrol-disablesegment-xaml' />

**2.** Disable a segment through the `SetSegmentEnabled(int index, bool isEnabled)` method:

<snippet id='segmentcontrol-disablesegment-setsegmentenabled' />

The following image shows the end result.

![.NET MAUI SegmentedControl disable segment](images/segmentcontrol-disablesegment.png)

>tip For a runnable example demonstrating the SegmentedControl Disable Segment scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **SegmentedControl > Disable Segment** category.

## See Also

- [Data Binding]({%slug segmentedcontrol-data-binding%})
- [Size Mode]({%slug segmentedcontrol-size-mode%})
- [Selection]({%slug segmentedcontrol-selection%})
- [Item Tapped]({%slug segmentedcontrol-item-tapped%})
- [Styling]({%slug segmentedcontrol-styling%})
