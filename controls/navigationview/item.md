---
title: Navigation Item
page_title: .NET MAUI NavigationView Documentation - Navigation Item
description: Discover the available configuration options of the Navigation Item and learn how to use them to customize the appearance and the behavior of the Telerik UI for .NET MAUI NavigationView control.
position: 6
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

>note The content area is scrollable, while the header and the footer are sticky.

## Setting Selection

The .NET MAUI `NavigationViewItem` exposes the following properties related to the item selection:

* `IsSelected` (`bool`)&mdash;Specifies a value indicating whether the navigation item is selected.
* `IsSelectable` (`bool`)&mdash;Specifies a value indicating whether the navigation item is selectable. The default value is `true`.

## Setting Custom Content

Customize the `NavigationViewItem` content by using the `ContentTemplate` (`DataTemplate`) property.

Here is an example with `ContentTemplate` property.

**1.** Define the `ContentTemplate` in the resources:

<snippet id='navigationview-navigationitem-contenttemplate' />

**2.** Set the `ContentTemplate` to the NavigationViewItem:

```XAML
<telerik:RadNavigationView x:Name="navigationView"
                            HeaderText="NavigationView Header">
    <telerik:RadNavigationView.Items>
        <telerik:NavigationViewItem Text="Search"
                                    Position="Header"
                                    ContentTemplate="{StaticResource SearchTemplate}"
                                    IsSelectable="False">
        </telerik:NavigationViewItem>
        <telerik:NavigationViewItem Text="Item 1" />
        <telerik:NavigationViewItem Text="Item 2" />
        <telerik:NavigationViewItem Text="Item 5" />
    </telerik:RadNavigationView.Items>
</telerik:RadNavigationView>
```

## Setting Visibility and Enabled State

Change the visibility of the `NavigationViewItem` by setting the `IsVisible` (`bool`) property.

Change the enabled state if the `NavigationViewItem` by setting the `IsEnabled` (`bool`) property.

## Configuring the Items

You can further configure the navigation items by using the `ControlTemplate` (`ControlTemplate`) property.

Here is an example with `ControlTemplate` property.

**1.** Define the `ControlTemplate` in the resources:

<snippet id='navigationview-navigationitem-controltemplate' />

**2.** Set the `ContentTemplate` to the NavigationViewItem:

```XAML
<telerik:RadNavigationView x:Name="navigationView"
                            HeaderText="NavigationView Header">
    <telerik:RadNavigationView.Items>
        <telerik:NavigationViewItem Text="Item 1" />
        <telerik:NavigationViewItem Text="Item 2" />
        <telerik:NavigationViewItem Text="Item 3" />
        <telerik:NavigationViewItem ControlTemplate="{StaticResource ItemTemplate}"/>
        <telerik:NavigationViewItem Text="Item 5" />
    </telerik:RadNavigationView.Items>
</telerik:RadNavigationView>
```

> For the runnable NavigationView Navigation Item example, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **NavigationView > Features > Pane Header and Footer example**.

## Events

The .NET MAUI `NavigationViewItem` exposes the following events:

* `Clicked`&mdash;Raised when the navigation item is clicked.The `Clicked` event handler receives two parameters:
	* The `sender` argument, which is of type `object`, but can be cast to the `NavigationViewItem`.
	* `System.EventArgs`.

* `IsSelectedChanged`&mdash; Raised when the NavigationViewItem `IsSelected` property has changed. The `IsSelectedChanged` event handler receives two parameters:
	* The `sender` argument, which is of type `object`, but can be cast to the `NavigationViewItem`.
	* `System.EventArgs`.

## Commands

* `Command` (`ICommand`)&mdash;Executed when the navigation item is clicked.
* `CommandParameter`&mdash;Specifies the parameter to the command which is executed when the navigation item is clicked.

## Styling

How to style the navigation items is described in the [NavigationItem Styling]({%slug navigationview-item-styling%}) article.

## See Also

- [Setting different Display Mode]({%slug navigationview-display-mode%})
- [Selecting an item]({%slug navigationview-selection%})
- [Configure the Navigation Pane]({%slug navigationview-pane%})
- [Configure the Navigation Header]({%slug navigationview-navigation-header%})
- [Navigation Item Styling]({%slug navigationview-item-styling%})
- [Navigation Pane Styling]({%slug navigationview-pane-styling%})
- [Navigation Header Styling]({%slug navigationview-styling%})
- [Events]({%slug navigationview-events%})
- [Commands]({%slug navigationview-commands%})