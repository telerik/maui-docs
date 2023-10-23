---
title: Navigation Pane
page_title: .NET MAUI NavigationView Pane Documentation - Navigation Pane
description: Learn what is the structure of the .NET MAUI NavigationView Pane and how to configure its header and footer.
position: 5
slug: navigationview-pane
---

# .NET MAUI NavigationView Pane

The Telerik UI for .NET MAUI NavigationView has a Pane containing the navigation items. The items can be positioned in the header, footer, or in the content (default) of the Pane element.

## Setting Items

Add items to the navigation pane by using the `Items` (`IList<NavigationViewItemBase>`) collection.

By default, the navigation items are added to the Pane content. By setting the `Position` property to the `NavigationViewItem` you can choose where to position the item.

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

You can define a custom template for the Pane header and footer by using the `PaneStyle` property. In the `PaneStyle`, set the `HeaderTemplate` (`ControlTemplate`) and `FooterTemplate`(`ControlTemplate`) properties. For more details, review the [Pane Styling]({%slug navigationview-pane-styling%}) article.

## Next Steps

How to style the header and footer of the Pane, review the [Pane Styling]({%slug navigationview-pane-styling%}) article.

## See Also

- [Setting different Display Mode]({%slug navigationview-display-mode%})
- [Selecting an item]({%slug navigationview-selection%})
- [Configure the Navigation Item]({%slug navigationview-items%})
- [Configure the Navigation Header]({%slug navigationview-navigation-header%})
- [Navigation Item Styling]({%slug navigationview-item-styling%})
- [Navigation Pane Styling]({%slug navigationview-pane-styling%})
- [Navigation Header Styling]({%slug navigationview-styling%})
- [Events]({%slug navigationview-events%})
- [Commands]({%slug navigationview-commands%})