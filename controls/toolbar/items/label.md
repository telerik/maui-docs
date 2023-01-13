---
title: Label
page_title: .NET MAUI Toolbar Documentation - Label ToolbarItem
description: "Review the Toolbar item label for .NET MAUI"
position: 0
slug: toolbar-items-label
---

# .NET MAUI Label ToolbarItem 

Add labels in the toolbar using the `LabelToolbarItem`.

The available properties for configuration are:

* `Text`(`string`)&mdash;Defines the text(target type `Label`) in the toolbar item. You can display an image next to the text.
* `ImageSource`(`Microsoft.Maui.Controls.ImageSource`)&mdash;Specifies the source of the image to display in the toolbar item.

## Styling

You can style the LabelToolbarItem using the `Style` property. The target type of the property should be `LabelToolbarItemView`. 

The available properties are:

* `Text`(`string`)&mdash;Specifies the text in the toolbar item.
* `TextColor`(`Microsoft.Maui.Graphics.Color`)&mdash;Secifies the color of the text in the toolbar item.
* `FontFamily`(`string`)&mdash;Secifies the font family of the text to display in the toolbar item.
* `FontSize`(`double`)&mdash;Secifies the font size of the text to display in the toolbar item. Default value is `16`.
* `FontAttributes`(enum of type `Microsoft.Maui.Controls.FontAttributes`)&mdash;Defines the font attributes of the text to display in the toolbar item. Default value is `None`.
* `TextDecorations`(enum of type `Microsoft.Maui.TextDecorations`)&mdash;Defines the decorations of the text to display in the toolbar item. Default value is `None`.
* `HorizontalTextAlignment`(enum of type `Microsoft.Maui.TextAlignment`)&mdash;Defines the horizontal alignment of the text to display in the toolbar item. The default value is `Start`.
* `VerticalTextAlignment`(enum of type `Microsoft.Maui.TextAlignment`)&mdash;Defines the vertical alignment of the text to display in the toolbar item. Default value is `Center`.
* `ImageSource`(`Microsoft.Maui.Controls.ImageSource`)&mdash;Defines the source of the image displayed in the in the toolbar item.
* `ImageAspect`(enum of type `Microsoft.Maui.Aspect`)&mdash;Defines the aspect ratio of the image displayed in the in the toolbar item. Default value is `Center`.
* `ImageWidth`(`double`)&mdash;Defines the width in pixels of the image displayed in the in the toolbar item. Default value is `-1.0`.
* `ImageHeight`(`double`)&mdash;Defines the height in pixels of the image displayed in the in the toolbar item. Default value is `-1.0`.
* `ImageSpacing`(`double`)&mdash;Defines the spacing in pixels between the image and the text displayed in the in the toolbar item. Default value is `8.0`.
* `DisplayOptions`(enum of type `Telerik.Maui.Controls.ToolbarItemDisplayOptions`) property allows you to display text, image in the toolbar or in a combination of both. The options are `Text` and `Image`. This enum type supports a bitwise combination of its members to enable morethan one option.

 Position the image relative to the text in the toolbar item by setting the `ImagePosition`(enum of type `Telerik.Maui.Controls.ToolbarItemImagePosition`). The available options are: 
	* `Left`&mdash;The image is displayed to the left of the text.
	* `Top`&mdash;The image is displayed at the top of the text.
	* `Right`&mdash;The image is displayed to the right of the text.
	* `Bottom`&mdash;The image is displayed at the bottom of the text.

* `HorizontalContentOptions`(enum of type `Microsoft.Maui.Controls.LayoutOptions`)&mdash;Specifies the horizontal alignment options of the content displayed in the toolbar item.
* `VerticalContentOptions`(enum of type `Microsoft.Maui.Controls.LayoutOptions`)&mdash;Specifies the vertical alignment options of the content displayed in the toolbar item.

All other properties that can be applied through style are the properties applicable for [ToolbarItemView]({%slug toolbar-items%}#styling).

## See Also

- [SplitButton ToolbarItem]({%slug toolbar-items-split-button%})
- [ToggleButton ToolbarItem]({%slug toolbar-items-toggle-button%})
- [NavigationButton ToolbarItem]({%slug toolbar-items-navigation-button%})
- [ListPicker ToolbarItem]({%slug toolbar-items-listpicker-button%})
- [Group ToolbarItem]({%slug toolbar-items-group%})
- [RadioButton ToolbarItem]({%slug toolbar-items-radio-button%})
- [Slider ToolbarItem]({%slug toolbar-items-slider%})
