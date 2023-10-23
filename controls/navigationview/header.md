---
title: Header
page_title: .NET MAUI NavigationView Documentation - Header
description: Learn more for the Navigation Header and how to customize its content.
position: 4
slug: navigationview-navigation-header
---

# .NET MAUI NavigationView Header

The Telerik UI for .NET MAUI NavigationView control has a navigation header. The header contains a toggle navigation button (for opening and closing the navigation page) and a navigation content (by default label with a text).

You can customize the header by setting the `HeaderText` or `HeaderTemplate` properties.

## Configuring the Header

* `HeaderText` (`string`)&mdash;Defines the text that is displayed in the NavigationView header.
* `HeaderTemplate` (`DataTemplate`)&mdash;Specifies the content template for the NavigationView header.
* `HeaderStyle` (`string`)&mdash;Specifies the style applied to the header, this includes the text and the navigation button. For more details, review the [NavigationView Header Styling]({%slug navigationview-styling%}) article.

### Example

Here is an example for `HeaderTemplate`:

**1.** Define the `RadNavigationView`:

<snippet id='navigationview-headertemplate' />

**2.** Define the `HeaderTemplate`:

<snippet id='navigationview-headertemplate' />

**3.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

## Toggle Navigation Button

The `NavigationViewToggleButton` represents a toggle button that opens or closes the `NavigationViewPane`. The button is part of the NavigationView header.

You can style the button through the `HeaderStyle` property of the `RadNavigationView`. For more details, review the [NavigationView Header Styling]({%slug navigationview-styling%}) article. 

> For the runnable NavigationView Header example, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **NavigationView > Features category**.

## See Also

- [Setting different Display Mode]({%slug navigationview-display-mode%})
- [Selecting an item]({%slug navigationview-selection%})
- [Configure the Navigation Pane]({%slug navigationview-pane%})
- [Configure the Navigation Item]({%slug navigationview-items%})
- [Navigation Item Styling]({%slug navigationview-item-styling%})
- [Navigation Pane Styling]({%slug navigationview-pane-styling%})
- [Navigation Header Styling]({%slug navigationview-styling%})
- [Events]({%slug navigationview-events%})
- [Commands]({%slug navigationview-commands%})
