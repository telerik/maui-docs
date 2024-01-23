---
title: Header and Footer
page_title: .NET MAUI CollectionView Documentation - Header and Footer
description: Learn how to define headers and footers in the Telerik UI for .NET MAUI CollectionView control and use them to adjust the position of the content.
position: 15
slug: collectionview-header-footer
---

# .NET MAUI CollectionView Header and Footer

The CollectionView provides the option to add - `Header` and `Footer`, which allow you to position the content of your choice above and below the list with the items. Both the header and footer are scrolled along with the CollectionView items.

By default, both the header and the footer are hidden:

* To visualize the header, set the `IsHeaderVisible` to `True`.
* To visualize the footer, set the `IsFooterVisible` to `True`.

## Setting the Header and Footer Content

Define the content for header and footer by setting the following properties:

* `Header`(`object`)&mdash;Specifies the header content which is displayed before all items.
* `Footer`(`object`)&mdash;Specifies the footer content which is displayed after all items.

Here is a sample CollectionView definition that sets the content for the `Header` and `Footer`:

<snippet id='collectionview-header-footer' />

> For a runnable demo with the CollectionView Header and Footer example, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **CollectionView > Header and Footer** category.

## Styling the Header and the Footer

To style the header and the footer, set the following properties:

* `HeaderStyle` (`Style` with target type `CollectionViewHeaderItemView`)&mdash;Specifies the style applied to the header when the `Header` property is set and `IsHeaderVisible` is set to `true`.
* `FooterStyle` (`Style` with target type `CollectionViewFooterItemView`)&mdash;Specifies the style applied to the footer when the `Footer` property is set and `IsFooterVisible` is set to `true`.

The following steps demonstrate how to define a sample CollectionView and to set the `HeaderStyle` and `FooterStyle`:

**1.** Define the CollectionView:

<snippet id='collectionview-header-footer-styling' />

**2.** Define the `HeaderStyle` definition in the page's resources:

<snippet id='collectionview-header-styling' />

**3.** Define the `FooterStyle` definition in the page's resources:

<snippet id='collectionview-footer-styling' />

> For a runnable demo with the CollectionView Header and Footer Styling example, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **CollectionView > Styling** category.

To apply the style selector to the header and footer, use the following properties:

* `HeaderStyleSelector` (`IStyleSelector` with target type `CollectionViewHeaderItemView`)&mdash;Specifies the style selector applied to the header when the `Header` property is set and `IsHeaderVisible` is set to `true`.
* `FooterStyleSelector` (`IStyleSelector` with target type `CollectionViewFooterItemView`)&mdash;Specifies the style selector applied to the footer when the `Footer` property is set and `IsFooterVisible` is set to `true`.

## Setting Templates for the Header and the Footer

* `HeaderTemplate`(`DataTemplate`)&mdash;Defines the Header of the CollectionView. It will be displayed before all items.
* `FooterTemplate`(`DataTemplate`)&mdash;Defines the Footer of the CollectionView. It will be displayed after all items.

Here is a sample CollectionView definition that uses a `HeaderTemplate` and `FooterTemplate`:

<snippet id='collectionview-header-footer-template' />

> For a runnable demo with the CollectionView Header and Footer Templates example, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **CollectionView > Header and Footer** category.

## See Also

- [Events]({%slug collectionview-events%})
- [Selection]({%slug collectionview-selection%})
