---
title: Selection
page_title: .NET MAUI NavigationView Documentation - Selection
description: Learn how to define selection in the .NET MAUI NavigationView control.
position: 7
slug: navigationview-selection
---

# .NET MAUI NavigationView Selection

NavigationView for .NET MAUI enables the app users to quickly select item from the navigation pane. This topic will go through the provided by the NavigationView API related to item selection.

NavigationView control has a support for single selection. 

## Main Properties

* `SelectedItem`(`object`)&mdash;Specifies the currently selected item in the navigation view. The property can be set to the NavigationView control.
* `IsSelectable`(`bool`)&mdash;Specifies whether the navigation item is selectable. The property can be set to the NavigationItem.
* `IsSelected`(`bool`)&mdash;Specifies whether the navigation item is selected. The property can be set to the NavigationItem.

## Events

NavigationView exposes a `SelectionChanged` event which is raised when the currently selected NavigationViewItem has changed. The `SelectionChanged` event handler receives two parameters:
	* The `sender` argument, which is of type `object`, but can be cast to the `RadNavigationView` control.
	* `System.EventArgs`.

## Example with Selection Properties

The example shows NavigationView Selection feature. 

**1.** Define the NavigationView control:

<snippet id='navigationview-selection' />

**2.** Add the `telerik` namespaces:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

## See Also

- [.NET MAUI NavigationView Product Page](https://www.telerik.com/maui-ui/navigationview)
- [.NET MAUI NavigationView Forum Page](https://www.telerik.com/forums/maui?tagId=1978)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
