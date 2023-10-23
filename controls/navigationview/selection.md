---
title: Selection
page_title: .NET MAUI NavigationView Documentation - Selection
description: Learn how to define the selection in the .NET MAUI NavigationView control.
position: 7
slug: navigationview-selection
---

# .NET MAUI NavigationView Selection

The NavigationView for .NET MAUI enables the app users to quickly select item from the navigation pane. This topic goes through the item selection API provided by the NavigationView component.

## Main Properties

* `SelectedItem`(`object`)&mdash;Specifies the currently selected item in the NavigationView. Set this property to the NavigationView.
* `IsSelectable`(`bool`)&mdash;Specifies whether the NavigationViewItem is selectable. Set this property to the NavigationViewItem.
* `IsSelected`(`bool`)&mdash;Specifies whether the NavigationViewItem is selected. Set this property to the NavigationViewItem.

## Events

NavigationView exposes a `SelectionChanged` event which is raised when the currently selected NavigationView item has changed. The `SelectionChanged` event handler receives two parameters:
* The `sender` argument, which is of type `object`, but can be cast to the `RadNavigationView` control.
* `System.EventArgs`.

## Example with Selection Properties

The following example shows the NavigationView Selection feature.

**1.** Define the NavigationView control:

<snippet id='navigationview-selection' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

This is how the NavigationView selection looks:

![Telerik UI for .NET MAUI NavigationView Selection](images/navigatioview-selection.png)

> For the runnable NavigationView Selection example, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **NavigationView > Features category**.

## See Also

- [Setting different Display Mode]({%slug navigationview-display-mode%})
- [Configure the Navigation Pane]({%slug navigationview-pane%})
- [Configure the Navigation Item]({%slug navigationview-items%})
- [Configure the Navigation Header]({%slug navigationview-navigation-header%})
- [Navigation Item Styling]({%slug navigationview-item-styling%})
- [Navigation Pane Styling]({%slug navigationview-pane-styling%})
- [Navigation Header Styling]({%slug navigationview-styling%})
- [Events]({%slug navigationview-events%})
- [Commands]({%slug navigationview-commands%})
