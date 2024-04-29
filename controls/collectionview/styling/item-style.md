---
title: Item Styling
page_title: .NET MAUI ListView Documentation - Item Styling
description: Check the Telerik for .NET MAUI CollectionView styling options for the Item Style.
position: 0
slug: collectionview-item-styling
tags: style,, item, collectionview, maui, dotnet maui
---

# .NET MAUI CollectionView Styling

To style the CollectionView, use the following properties:

* `BackgroundColor` (`Color`)&mdash;Specifies the background color of the control.

## Styling and Configuring the Item

The CollectionView control provides a styling mechanism for customizing the look of its items. To use it, set the `ItemViewStyle` (`Style` with a target type `RadCollectionViewItemView `) property of the control.

The available properties are described in the table below:

| Property | Description |
| -------- | ----------- |
| `BackgroundColor`(`Color`) | Defines the background color of the item. |
| `Padding` (`Thickness`) | Defines the padding of the item. |
| `IsSelected` (`bool`) | Defines whether the item is selected. Default value is `false`. |
| `GroupLevelIndentation` (`double`) | Defines the indentation that accumulates for each group level. |
| `BorderBrush` (`Brush`) | Defines the brush of the border around the item. |
| `BorderColor` (`Color`) | Defines the color of the border around the item. |
| `BorderThickness` (`Thickness`) | Defines the thickness of the border around the item. |
| `CornerRadius` (`Thickness`) | Defines the corner radius of the border around the item. |
| `ControlTemplate`(`DataTemplate`) | Specifies the `DataTemplate` of the visual representation of the current item. When set to `null`, the control displays the text representation of the current item. |

The following example shows how to use the `ItemViewStyle`:

**1.** Define the following business object:

<snippet id='collectionview-datamodel' />

**2.** Create a `ViewModel` class as shown below:

<snippet id='collectionview-viewmodel' />

**3.** Add the `RadCollectionView` definition with the `ItemViewStyle` set:

<snippet id='collectionview-item-container-styling' />

**4.** Include the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" 
```

**5.** Add the following styles to the page's resource:

<snippet id='collectionview-item-container-style-resources' />

> For a runnable example demonstrating the CollectionView ItemView Styling, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **CollectionView > Styling** category.

## See Also

- [Item Appearance]({%slug collectionview-item-appearance%})
- [Grouping]({%slug collectionview-grouping%})
- [Filtering]({%slug collectionview-filtering%})
- [Sorting]({%slug collectionview-sorting%})
- [Selection]({%slug collectionview-selection%})
- [Commands]({%slug collectionview-commands%})
- [Events]({%slug collectionview-commands%})

