---
title: Header ItemStyle Selector
page_title: .NET MAUI TabView Documentation - Header ItemStyle Selector
description: Learn how to apply a style selector to the header items of the Telerik UI for .NET MAUI TabView.
slug: tabview-header-itemstyle-selector
tags: tabview, maui, dotnet, header, styleselector
position: 3
---

# .NET MAUI TabView Header ItemStyle Selector

Through the `HeaderItemStyleSelector` property you can apply different styles to each TabView header item. The target type of the Style must be `TabViewHeaderItem`.

**1.** Define the TabView control:

<snippet id='tabview-styling-headeritemstyleselector' />

**2.** Define the `StylSelector` resources:

<snippet id='tabview-styling-styleselector-resources' />

**3.** Define the `StylSelector` class:

<snippet id='tabview-header-styleselector-class' />

Here is the TabView after applying the `HeaderItemStyleSelector`:

![.NET MAUI TabView Header Item Style Selector](images/styling-headeritemstyleselector.png)

> For a runnable example with the TabView `HeaderItemStyleSelector` scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **TabView > Styling**.

## See Also

- [Styling the Header]({%slug tabview-header-styling%})
- [Styling the Header Item]({%slug tabview-header-item-styling%})
- [Styling the TabView Content]({%slug tabview-content-styling%})