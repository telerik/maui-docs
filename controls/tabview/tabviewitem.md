---
title: TabViewItem
page_title: .NET MAUI TabView Documentation - TabViewItem
description: Check the Telerik UI for .NET MAUI TabViewItem control used to populate the TabView.
slug: tabview-item
tags: tabview, overview
position: 6
---

# TabViewItem

`TabViewItem` is the control used to populate the TabView. It displays the header of the tab item and the corresponding content. `TabViewItem` exposes the following properties:

* `HeaderText` (`string`)&mdash;Defines a simple text for the TabView item.
* `ImageSource` (`ImageSource`)&mdash;Specifies the source of the image icon in the header item.
* `IsSelected` (`bool`)&mdash;Indicated whether the item is selected.
* `IsEnabled` (`bool`)&mdash;Defines whether the TabView Item is enabled/disabled. By default `IsEnabled` is `True`.
* `IsVisible` (`bool`)&mdash;Specifies whether the TabView Item is visible/hidden. 
* `Content` (`Microsoft.Maui.Controls.View`)&mdash;Defines the content of the TabView Item. You can use any UI element that implements the View class.
* `ContentTemplate` (`DataTemplate`)&mdash;Defines the content template that is displayed when the current tab is selected.

## Displaying TabViewItem

To display a `TabViewItem` you can add it in the `Items` collection of `TabView` or using the [TabView ItemsSource]({%slug tabview-data-binding%}).

#### Example

The following example shows how to add TabView items directly to the Items collection:

```XAML
<telerik:RadTabView x:Name="tabView">
	<telerik:TabViewItem HeaderText="Home" />
	<telerik:TabViewItem HeaderText="Folder" />
	<telerik:TabViewItem HeaderText="View" />
</telerik:RadTabView>
```

## Defining Content

You can define the content of a `TabViewItem` via its `Content` property or `ContentTemplate` property. 

#### Example with Content property

<snippet id='tabview-getting-started-xaml' />

> The TabView control displays only the content of the selected item.

## See Also

- [Selection]({%slug tabview-selection%})
- [Styling]({%slug tabview-styling%})
