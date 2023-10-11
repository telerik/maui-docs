---
title: Navigation Item
page_title: .NET MAUI NavigationView Documentation - Navigation Item
description: Discover the available configuration options of the Navigation Item and learn how to use them to customize the appearance and the behavior of the Telerik UI for .NET MAUI NavigationView control.
position: 5
slug: navigationview-items
---

# .NET MAUI NavigationView Item

This articles explains the configuration options of the `NavigationViewItem`.

## Setting Text

Display text in the `NavigationViewItem` by setting the `Text` (`string`) property.

## Setting Image

Display image in the `NavigationViewItem` by setting the `ImageSource` (`Microsoft.Maui.Controls.ImageSource`) property.

## Setting Position

You can configure the navigation items position by adding them to the Pane header, footer or to the content.

* `Position` (enum of type `Telerik.Maui.Controls.NavigationView.NavigationViewItemPosition`)&mdash;Specifies the position of the navigation item. the available options are: 
	* Default `Content`&mdash;The navigation item is placed in the content area of the `NavigationViewPane` control.
	* `Header`&mdash;The navigation item is placed in the header area of the `NavigationViewPane` control.
	* `Footer`&mdash;The navigation item is placed in the footer area of the `NavigationViewPane` control.

## Setting Selection

The .NET MAUI `NavigationViewItem` exposes the following properties related to the item selection:

* `IsSelected` (`bool`)&mdash;Specifies a value indicating whether the navigation item is selected.
* `IsSelectable` (`bool`)&mdash;Specifies a value indicating whether the navigation item is selectable. The default value is `true`.

## Setting Custom Content

Customize the `NavigationViewItem` content by using the `ControlTemplate` (`ControlTemplate`) property.

## Setting Visibility and Enabled State

Change the visibility of the `NavigationViewItem` by setting the `IsVisible` (`bool`) property.

Change the enabled state if the `NavigationViewItem` by setting the `IsEnabled` (`bool`) property.

## Configuring the Items

You can further configure the navigation items by using the `ContentTemplate` (`DataTemplate`) property, and customize the NavigationViewItem by using the `ControlTemplate` (`ControlTemplate`) property.

Here is an example with `ContentTemplate` property.

<snippet id='navigationview-navigationitem-contenttemplate' />

Here is an example with `ControlTemplate` property.

<snippet id='navigationview-navigationitem-controltemplate' />

## Events

The .NET MAUI `NavigationViewItem` exposes the following events:

* `Clicked`&mdash;Raised when the navigation item is clicked.The `Clicked` event handler receives two parameters:
	* The `sender` argument, which is of type `object`, but can be cast to the `NavigationViewItem`.
	* `System.EventArgs`.

* `IsSelectedChanged`&mdash; Raised when the NavigationViewItem IsSelected property has changed. The `IsSelectedChanged` event handler receives two parameters:
	* The `sender` argument, which is of type `object`, but can be cast to the `NavigationViewItem`.
	* `System.EventArgs`.

## Commands

* `Command` (`ICommand`)&mdash;Executed when the navigation item is clicked.
* `CommandParameter`&mdash;Specifies the parameter to the command which is executed when the navigation item is clicked.

## Styling

How to style the navigation items is described in the [NavigationItem Styling]({%slug navigationview-item-styling%}) article.

## See Also

- [.NET MAUI NavigationView Forum Page](https://www.telerik.com/forums/maui?tagId=1978)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
