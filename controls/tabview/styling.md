---
title: Styling
page_title: .NET MAUI TabView Documentation | Styling
description: TabView Styling documentation.
slug: tabview-styling
tags: tabview, overview
position: 15
---

# Styling

TabView provides means for modifying its visual appearance, so that it matches the style of the app.  You can style different parts of the TabView - its header, items and content area. 

> Check the [TabView Visual Structure]({%slug tabview-visual-structure%}) topic for a visual representation of the TabView elements.


## TabView Styling

You can use any of the following TabView properties to change its look&amp;feel:

* `BackgroundColor`
* `BorderColor`
* `BorderThickness` 
* `CornerRadius`
* `ContentPadding`

In addition, TabView provides the listed below styling properties for modifying its elements - header, TabView items and content area.

* `HeaderStyle` - specifies the style of the entire header area (border, background color etc.);
* `HeaderItemStyle` - specifies the style of the individual header items (font, text color etc.)
* `ContentStyle` - specifies the style of the entire content area (borders, background color etc.);

## Header Styling

Through `HeaderStyle` property of the TabView you can modify the `TabViewHeader`. `TabViewHeader` provides the following properties:

* `Orientation`(`Telerik.Maui.Controls.TabViewScrollOrientation`)&mdash;Specifies the tabview items orientation - can be horizontal or vertical;
* `Position`(`Telerik.Maui.Controls.TabViewHeaderPosition`)&mdash;Controls the position of the header - can be top, bottom left or right;
* `Spacing`(`double`)&mdash;Applies spacing in pixels between the header area and the content area;
* `IsScrollable`&mdash;Enables scrolling through the tabs inside the TabView Header.
      
## HeaderItem Styling

Through `HeaderItemStyle` property of the TabView the following styling properties can be applied to the `TabViewHeaderItem`:

* `BackgroundColor` - specifies the background color of the header item
* `BorderColor` - specifies the border color of the header item
* `BorderThickness` - specifies the border thickness of the header item
* `CornerRadius` - specifies the corner radius of the header item
* `ContentPadding` - specifies the padding of the inner content of the header item
* `TextColor` - specifies the color of the text in the header item
* `FontFamily` - specifies the font family of the text in the header item
* `FontSize` - specifies the font size of the text in the header item
* `FontAttributes` - specifies the font attributes of the text in the header item
* `TextDecorations` - specifies the decorations of the text in the header item
* `HorizontalTextAlignment` - specifies the horizontal alignment of the text in the header item
* `VerticalTextAlignment` - specifies the vertical alignment of the text in the header item
* `ImageSource` - specifies the source of the image icon in the header item
* `ImageAspect` - specifies the aspect of the image icon in the header item
* `ImageWidth` - specifies the width of the image icon in the header item
* `ImageHeight` - specifies the height of the image icon in the header item
* `ImageSpacing` - specifies the spacing between the image icon and the text in the header item
* `ImagePosition` - specifies the position of the image icon relative to the text (Left, Top, Right, Bottom)

## Content Styling

TabView's `ContentStyle` property allows you to style the content area. `TabViewContent` provides the following properties:

* `IsSwipeEnabled`&mdash;Controls whether it will be possible to swipe through the tabs' content;
* `BackgroundColor`
* `BorderColor`
* `BorderThickness` 
* `CornerRadius`
* `ContentPadding`

## See Also

- [TabViewItem]({%slug tabview-item%})
- [Selection]({%slug tabview-selection%})
- [Templates]({%slug tabview-templates%})