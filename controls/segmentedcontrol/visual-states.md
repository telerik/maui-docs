---
title: Visual States
page_title: .NET MAUI SegmentedControl Documentation - Visual States
description: Learn how to configure the visual states of the Telerik SegmentedControl for .NET MAUI, including Normal, Selected, MouseOver, and Disabled states.
position: 10
tags: .net maui, telerik .net maui, ui for .net maui, segmentedcontrol, microsoft .net maui
slug: segmentedcontrol-visual-states
---

# .NET MAUI SegmentedControl Visual States

This article describes the visual states the SegmentedControl provides. 
You can use the visual states to change the appearance of the control depending on whether it is disabled, selected, or has the mouse pointer hovering over it.

The SegmentedControl provides the following `CommonStates` visual states:

| Visual States | Description |
| ------------- | --------------- |
| `Normal` | Applies when the segment is in normal state. |
| `Pressed` | Applies when the segment is pressed. |
| `SelectedPressed` | Applies when the segment is selected and pressed. |
| `MouseOver` | (Desktop-only) Applies when the mouse pointer hovers over the segment. |
| `SelectedMouseOver` | (Desktop-only) Applies when the segment is selected and the mouse pointer hovers over it. |
| `FocusedMouseOver` | (Desktop-only) Applies when the segment is focused with the keyboard and the mouse pointer hovers over it. |
| `Selected` | Applies when the segment is selected. |
| `FocusedSelected` | (Desktop-only) Applies when the segment is selected and focused with the keyboard. |
| `Focused` | (Desktop-only) Applies when the segment is focused. |
| `Disabled` | Applies when the segment is disabled. |
| `DisabledSelected` | Applies when the segment is disabled and selected. |

All `MouseOver` and `Focused` visual states are used in keyboard navigation support and desktop scenarios. They do not apply in mobile scenarios, where the touch interaction model does not have the concept of hovering or keyboard focus.

## See Also

- [Styling the SegmentedControl]({%slug segmentedcontrol-styling%})