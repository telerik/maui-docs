---
title: Item Tapped
page_title: .NET MAUI SegmentedControl Documentation - Item Tapped
description: Learn how to respond to tap interactions on the segments of the Telerik UI for .NET MAUI SegmentedControl through the ItemTapped event and the ItemTappedCommand command.
position: 6
slug: segmentedcontrol-item-tapped
---

# .NET MAUI SegmentedControl Item Tapped

The SegmentedControl notifies you about tap interactions on its segments independently of the current selection. This allows you to handle taps on segments that are already selected, or to react to user interaction when the [`SelectionMode`]({%slug segmentedcontrol-selection%}#selection-modes) is set to `None`.

The control exposes the following members for responding to tap interactions:

* `ItemTapped`&mdash;Event raised when a segment is tapped, regardless of the `SelectionMode`. The event handler receives a `RadTappedEventArgs<object>` argument whose `Item` property is the tapped business item.
* `ItemTappedCommand` (`ICommand`)&mdash;Command executed when a segment is tapped. The command parameter is the data item of the tapped segment.

> The `ItemTapped` event and the `ItemTappedCommand` command are raised for every tap, including taps on the currently selected segment. Use them when you need to perform an action on each tap rather than only when the selection changes. To react to selection changes, use the [`SelectionChanged`]({%slug segmentedcontrol-selection%}#selection-events) event instead.

>tip For a runnable example demonstrating the SegmentedControl Item Tapped scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **SegmentedControl > Item Tapped** category.

## See Also

- [Data Binding]({%slug segmentedcontrol-data-binding%})
- [Size Mode]({%slug segmentedcontrol-size-mode%})
- [Selection]({%slug segmentedcontrol-selection%})
- [Disabled Segments]({%slug segmentedcontrol-disable-segment%})
- [Styling]({%slug segmentedcontrol-styling%})
