---
title: Button
page_title: .NET MAUI Toolbar Documentation - Button ToolbarItem
description: "Review the Toolbar button item for .NET MAUI"
position: 2
slug: toolbar-items-button
---

# .NET MAUI Button ToolbarItem

Add buttons in the toolbar using the `ButtonToolbarItem`.

The available properties for configuration are:

* `Text`(`string`)&mdash;Defines the text(target type `Label`) in the toolbar item. You can display an image next to the text.
* `ImageSource`(`Microsoft.Maui.Controls.ImageSource`)&mdash;Specifies the source of the image to display in the toolbar item.

```XAML
<telerik:ButtonToolbarItem Text="Undo">
    <telerik:ButtonToolbarItem.ImageSource>
        <FontImageSource Glyph="{x:Static telerik:TelerikFont.IconUndo}"
                            FontFamily="{x:Static telerik:TelerikFont.Name}"
                            Size="16" />
    </telerik:ButtonToolbarItem.ImageSource>
</telerik:ButtonToolbarItem>
```

## Events

The exposed events are:

* `Clicked`&mdash:Raised when the button is clicked.

## Commands

The available commands are:

* `Command`(`ICommand`)&mdash;Specfies the command to execute when the button is clicked.
* `CommandParameter`(`object`)&mdash;Specfies the parameter of the command, which is executed when the button is clicked.

## Styling

ButtonToolbarItem has a `Style` property with target type `ButtonToolbarItemView`. The properties exposed in the `ButtonToolbarItemView` are `Command`, `CommandParameter`, `Clicked` event.

All other properties that can be applied through style are the properties applicable for [ToolbarItemView]({%slug toolbar-items%}#styling) and [LabelToolbarItemView]({%slug toolbar-items-label%}#styling).

<snippet id='imageeditor-styling-button-toolbar-style'/>

## See Also

- [SplitButton ToolbarItem]({%slug toolbar-items-split-button%})
- [ToggleButton ToolbarItem]({%slug toolbar-items-toggle-button%})
- [Label ToolbarItem]({%slug toolbar-items-label%})
- [NavigationButton ToolbarItem]({%slug toolbar-items-navigation-button%})
- [ListPicker ToolbarItem]({%slug toolbar-items-listpicker-button%})
- [Group ToolbarItem]({%slug toolbar-items-group%})
- [RadioButton ToolbarItem]({%slug toolbar-items-radio-button%})
- [Slider ToolbarItem]({%slug toolbar-items-slider%})

