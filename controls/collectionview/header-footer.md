---
title: Header and Footer
page_title: .NET MAUI CollectionView Documentation - Header and Footer
description: Learn how to add header and footer to the Telerik UI for .NET MAUI CollectionView.
slug: collectionview-header-footer
tags: .net maui, maui, collectionview, header, footer, headertemplate, footertemplate
---

# .NET MAUI CollectionView Header and Footer

The .NET MAUI CollectionView provides the option to add `HeaderTemplate` and `FooterTemplate`, which will allow you to position content of your choice above and below the list with the items. Both header and footer templates are scrolled along with the CollectionView items.

* `HeaderTemplate`(`DataTemplate`)&mdash;Defines the Header of the CollectionView before all items.
* `FooterTemplate`(`DataTemplate`)&mdash;Defines the Footer of the CollectionView after all items.

The following example shows how to add a Header and a Footer to the CollectionView control.

**1.** Add the CollectionView instance with the `HeaderTemplate` and `FooterTemplate` applied:

<snippet id='collectionview-header-footer'/>

**2.** Add a sample `ViewModel` class with a list of `DataModel` objects which is used as a BindingContext of the CollectionView:

<snippet id='collectionview-viewmodel'/>

**3.** Add the `DataModel` class:

<snippet id='collectionview-datamodel'/>

The following image shows how the CollectionView Header looks.

![.NET MAUI CollectionView Header Template](images/collectionview-header-template.png)

The following image shows how the CollectionView Footer looks.

![.NET MAUI CollectionView Footer Template](images/collectionview-footer-template.png)

## See Also

- [Selection]({%slug collectionview-selection%})
- [Scrolling]({%slug collectionview-scrolling%})
- [Pull To Refresh]({%slug collectionview-pull-to-refresh%})
