---
title: Navigation Pane
page_title: .NET MAUI NavigationView Pane Documentation - Navigation Pane
description: Lear what is the structure of the .NET MAUI NavigationView Pane and how to configure its header and footer.
position: 5
slug: navigationview-pane
---

# .NET MAUI NavigationView Pane

The Telerik UI for .NET MAUI NavigationView has a Pane. The Pane contains the navigation items. The items can be positioned to the header, footer or by default in the content of the Pane element.

## Setting Items

Add items to the navigation pane by using the `Items` (`IList<NavigationViewItemBase>`) collection.

By default the navigation items are added to the Pane content. By setting the `Position` property to the NavigationViewItem you can choose where to position the item. 

## Adding Items to Header and Footer

* Add navigation items to the header of the Pane by setting the `Position` to `Header`.

Here is an example:

```XAML
<telerik:NavigationViewItem Text="Item 1" 
                            Position="Header"/>
```

* Add navigation items to the footer of the Pane by setting the `Position` to `Footer`.

Here is an example:

```XAML
<telerik:NavigationViewItem Text="Item 1" 
                            Position="Footer"/>
```

>note If `Position` is not set, the items are added to the content of the Pane.

## Customizing the Header and Footer

You can define custom template for Pane header and footer by using the `PaneStyle` property. In the `PaneStyle` set the `HeaderTemplate` (`ControlTemplate`) and `FooterTemplate`(`ControlTemplate`) properties. For more details, review the [Pane Styling]({%slug navigationview-pane-styling%}) article.

### Style the Overlay

Set a brush for the overlay by using the `DismissOverlayBrush` (`Brush`) property.

Set a color for the overlay by using the `DismissOverlayColor` (`Color`) property.

## Styling

How to style the header and footer of the Pane, review the [Pane Styling]({%slug navigationview-pane-styling%}) article.

## See Also

- [.NET MAUI NavigationView Forum Page](https://www.telerik.com/forums/maui?tagId=1978)
- [Telerik .NET MAUI Blogs](https://www.telerik.com/blogs/mobile-net-maui)
- [Telerik .NET MAUI Roadmap](https://www.telerik.com/support/whats-new/maui-ui/roadmap)
