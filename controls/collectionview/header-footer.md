---
title: Header and Footer
page_title: .NET MAUI CollectionView Documentation - Header and Footer
description: Learn more about header and footer definition for the Telerik UI for .NET MAUI CollectionView control.
position: 8
slug: collectionview-header-footer
---

# .NET MAUI CollectionView Header and Footer

The CollectionView provides the option to add - `Header` and `Footer`, which will allow you to position content of your choice above and below the list with the items. Both header and footer are scrolled along with the CollectionView items.

## Header and Footer Visibility

By default both the header and the footer are hidden. To visualize the header set the `IsHeaderVisible` to `true` and to visualize the footer, set the `IsFooterVisible` to `true`. 

## Setting Direct Content to the Header and the Footer

Define content to the header and footer by setting the following properties:

* `Header`(`object`)&mdash;Specifies the header content which is displayed before all items.
* `Footer`(`object`)&mdash;Specifies the footer content which is displayed after all items.

## Styling the Header and the Footer

Style the header and the footer by setting the following properties:

* `HeaderStyle`(`Style` with target type `CollectionViewHeaderItemView`)&mdash;Specifies the style applied to the header when `Header` property is set and `IsHeaderVisible` is set to `true`.
* `FooterStyle`(`Style` with target type `CollectionViewFooterItemView`)&mdash;Specifies the style applied to the footer when `Footer` property is set and `IsFooterVisible` is set to `true`.

Apply style selector to the header and footer by setting the following properties:

* `HeaderStyleSelector`(`IStyleSelector` with target type `CollectionViewHeaderItemView`)&mdash;Specifies the style selector applied to the header when `Header` property is set and `IsHeaderVisible` is set to `true`.
* `FooterStyleSelector`(`IStyleSelector` with target type `CollectionViewFooterItemView`)&mdash;Specifies the style selector applied to the footer when `Footer` property is set and `IsFooterVisible` is set to `true`.

## Setting Templates to the Header and the Footer

* `HeaderTemplate`(`DataTemplate`)&mdash;Defines the Header of the CollectionView before all items.
* `FooterTemplate`(`DataTemplate`)&mdash;Defines the Footer of the CollectionView after all items.

## See Also

- [Events]({%slug collectionview-events%})
- [Selection]({%slug collectionview-selection%})
