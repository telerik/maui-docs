---
title: Events
page_title: .NET MAUI NavigationView Documentation - Events
description: Lear more about the NavigationView events that are raised when pane is opened, closed and item is clicked and selected.
position: 10
slug: navigationview-events
---

# .NET MAUI NavigationView Events

The .NET MAUI NavigationView emits a set of events that allow you to configure the component's behavior in response to specific user actions.

The .NET MAUI NavigationView exposes the following events:

* The `SelectionChanged`&mdash;Raised when the currently selected NavigationViewItem has changed. The `SelectionChanged` event handler receives two parameters:
	* The `sender` argument, which is of type `object`, but can be cast to the `RadNavigationView` control.
	* `System.EventArgs`.

* The `ItemClicked`&mdash;Raised when the NavigationViewItem is clicked. The `ItemClicked` event handler receives two parameters:
	* The `sender` argument, which is of type `object`, but can be cast to the `RadNavigationView` control.
	* `NavigationItem` (`Telerik.Maui.Controls.NavigationView.NavigationViewItem`)&mdash;Gets the NavigationViewItem for which the interaction is performed.

* The `PaneOpened`&mdash;Raised when the Pane open animation completes. The `PaneOpened` event handler receives two parameters:
	* The `sender` argument, which is of type `object`, but can be cast to the `RadNavigationView` control.
	* `System.EventArgs`.

* The `PaneClosed`&mdash;Raised when the Pane close animation completed. The `PaneClosed` event handler receives two parameters:
	* The `sender` argument, which is of type `object`, but can be cast to the `RadNavigationView` control.
	* `System.EventArgs`.

## Example with All Events Described in the Article:

**1.** Define the NavigationView control:

<snippet id='navigationview-events' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** The `SelectionChanged` implementation:

<snippet id='navigationview-events-selectionchanged' />

**4.** The `ItemClicked` implementation:

<snippet id='navigationview-events-itemclicked' />

**5.** The `PaneOpened` implementation:

<snippet id='navigationview-events-paneopened' />

**6.** The `PaneClosed` implementation:

<snippet id='navigationview-events-paneclosed' />

> For the runnable NavigationView Events example, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **NavigationView > Events category**.

## See Also

- [Setting different Display Mode]({%slug navigationview-display-mode%})
- [Selecting an item]({%slug navigationview-selection%})
- [Configure the Navigation Pane]({%slug navigationview-pane%})
- [Configure the Navigation Item]({%slug navigationview-items%})
- [Configure the Navigation Header]({%slug navigationview-navigation-header%})
- [Navigation Item Styling]({%slug navigationview-item-styling%})
- [Navigation Pane Styling]({%slug navigationview-pane-styling%})
- [Navigation Header Styling]({%slug navigationview-styling%})
- [Commands]({%slug navigationview-commands%})