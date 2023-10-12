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

**2.** Add the `telerik` namespaces:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

## See Also

- [.NET MAUI NavigationView Forum Page](https://www.telerik.com/forums/maui?tagId=1978)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
