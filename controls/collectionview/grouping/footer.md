---
title: Group Footer
page_title: .NET MAUI CollectionView Documentation - Group Footer
description: Check the Telerik UI for .NET MAUI CollectionView GroupFooter's BindingContext properties and how to style and define a custom GroupFooterTemplate.
position: 5
slug: collectionview-group-footer
tags: group, collectionview, groupdescriptor, custom group footer
---

# .NET MAUI CollectionView Group Footer

The CollectionView allows you to display a group footer when grouping is applied. You can visualize the group footer by setting the `IsGroupFooterVisible` to `True`.

The `BindingContext` of the `GroupFooter` is a complex object and it includes the following properties:

- `IsExpanded`&mdash;Defines a value indicating whether the group is currently expanded (has its child items visible).
- `Items`&mdash;Gets the child items of the group.
- `Key`&mdash;Gets the specific for the group key.
- `Level`&mdash;Gets the zero-based level (or the depth) of the group.

## Styling the Group Footer

The CollectionView control for .NET MAUI provides the following styling properties for customizing the appearance of its footer:

* `GroupFooterStyle`(`Style` with target type `CollectionViewGroupFooterItemView`)&mdash;Specifies the style applied to the group footer.
* `GroupFooterStyleSelector`(`Style` with target type `CollectionViewGroupFooterItemView`)&mdash;Specifies the style selector for the group footer.

## Customizing the Group Footer

If the default look how the group footer is presented do not match your use case, you can define custom templates by setting the `GroupFooterTemplate` property.

## Example with GroupFooterTemplate
 
**1.** Define the following business object:

<snippet id='collectionview-datamodel' />

**2.** Create a `ViewModel` class as shown below:

<snippet id='collectionview-viewmodel' />

**3.** Add the `RadCollectionView` definition with `GroupFooterTemplate`:

<snippet id='collectionview-group-header-footer' />

**4.** Include the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" 
```

> For a runnable demo with the CollectionView GroupFooterTemplate, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **Calendar > Grouping** category.

## See Also

- [Property Group Descriptor]({%slug collectionview-property-group-descriptor%})
- [Bindable Group Descriptors]({%slug collectionview-bindable-group-descriptor%})
- [Multi-level Grouping Descriptor]({%slug collectionview-grouping-multilevel%})
- [Group Header]({%slug collectionview-group-header%})