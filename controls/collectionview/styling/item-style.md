---
title: Item Styles
page_title: .NET MAUI ListView Documentation - Item Styles
description: Check the Telerik for .NET MAUI CollectionView styling options for the Item Style.
position: 0
slug: collectionview-item-styling
tags: style,, item, collectionview, maui, dotnet maui
---

# .NET MAUI CollectionView Styling

To style the CollectionView, use the following properties:

* `BackgroundColor`(`Color`)&mdash;Specifies the background color of the control.
* `BorderColor`(`Color`)&mdash;Specifies the border color of the control.
* `BorderBrush`(`Color`)&mdash;Specifies the border brush of the control.
* `BorderThickness`(`Thickness`)&mdash;Specifies the border thickness of the control.
* `CornerRadius`(`Thickness`)&mdash;Specifies the corner radius of the control.
* `ContentPadding`(`Thickness`)&mdash;Specifies the content padding of the control.

## Styling and Configuring the Item

The CollectionView control provides styling mechanism for customizing the look of its items.
To use it, set the `ItemStyle` property of the control with a target type `ItemView`.

The available properties are described in the table below:

| Property | Description |
| -------- | ----------- |
| `BackgroundColor`(`Color`) | Defines the background color of the item. |
| `BorderBrush`(`Brush`) | Defines the brush of the border around the item. |
| `BorderColor`(`Color`) | Defines the color of the border around the item. |
| `BorderThickness`(`Thickness`) | Defines the thickness of the border around the item. |
| `CornerRadius`(`Thickness`) | Defines the corner radius of the border around the item. |
| `ContentPadding`(`Thickness`) | Defines the padding of the content in the item. |
| `TextColor`(`Color`)&mdash;Defines the color of the text in the item. |
| `FontSize`(`double`) | Defines the size of the text in the item. |
| `FontFamily`(`string`) | Defines the font family of the displayed text. |
| `FontAttributes`(`FontAttributes`) | Defines the font attributes of the displayed text. |
| `TextDecorations`(`TextDecorations`) | Defines the text decorations of the displayed text. |
| `HorizontalTextAlignment`(`TextAlignment`) | Defines the horizontal alignment of the displayed text. |
| `VerticalTextAlignment`(`TextAlignment`) | Defines the vertical alignment of the displayed text. |
| `HorizontalContentOptions`(`LayoutOptions`) | Defines the horizontal layout options of the displayed content. |
| `VerticalContentOptions`(`LayoutOptions`) | Defines the vertical layout options of the displayed content. |
| `ContentTemplate`(`DataTemplate`) | Specifies the `DataTemplate` of the visual representation of the current item. When set to `null`, the control displays the text representation of the current item. |


## See Also

