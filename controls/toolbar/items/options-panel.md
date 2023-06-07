---
title: OptionsButton
page_title: .NET MAUI Toolbar Documentation - OptionsButton ToolbarItem
description: "Review the Toolbar control for .NET MAUI"
position: 9
slug: toolbar-items-overflow
---

# .NET MAUI OptionsButton ToolbarItem

Use the `OptionsButtonToolbarItem` for displaying an options panel in the Toolbar control. The toolbar item has to be attached to the `RadToolbarOptionsPanel`.

<snippet id='toolbar-optionspanel-item'/>

And the RadToolbarOptionsPanel definition:

```XAML
<telerik:RadToolbarOptionsPanel x:Name="topPanel" />
```

* `OptionsPanel`(`Telerik.Maui.controls.RadToolbarOptionsPanel`)&mdash;Specifies the options panel associated with this toolbar item.
* `OptionsContentStyle`(`Telerik.Maui.controls.RadToolbarOptionsPanel`)&mdash;Specifies the style of the options content. The target type of this style is `Telerik.Maui.Controls.OptionsButtonToolbarItemViewContent`.
* `OptionsContentTemplate`(`Microsoft.Maui.Controls.ControlTemplate`)&mdash;Specifies the template of the options content. The target type of this style is `Telerik.Maui.Controls.The target type of this template is Telerik.Maui.Controls.OptionsButtonToolbarItemViewContent`.
* `Text`(`string`)&mdash;Defines the text(target type `Label`) in the toolbar item. You can display an image next to the text.
* `ImageSource`(`Microsoft.Maui.Controls.ImageSource`)&mdash;Specifies the source of the image to display in the toolbar item.

>note Use the properties available in the [DropDownButtonToolbarItem]({%slug toolbar-items-dropdown-button%}) as the OptionsButtonToolbarItem inherits from it. 

## Events

The exposed events are:

* `Clicked`&mdash;Raised when the button is clicked.

## Commands

The available commands are:

* `Command`(`ICommand`)&mdash;Specfies the command to execute when the button is clicked.
* `CommandParameter`(`object`)&mdash;Specfies the parameter of the command, which is executed when the button is clicked.

## Styling

Use the `Style` property with target type `OptionsButtonToolbarItemView`. The available proeprties that can be applied through Style are: 

* `OptionsPanel`(`Telerik.Maui.controls.RadToolbarOptionsPanel`)&mdash;Specifies the options panel associated with this toolbar item.
* `OptionsContentStyle`(`Telerik.Maui.controls.RadToolbarOptionsPanel`)&mdash;Specifies the style of the options content. The target type of this style is `Telerik.Maui.Controls.OptionsButtonToolbarItemViewContent`.
* `OptionsContentTemplate`(`Microsoft.Maui.Controls.ControlTemplate`)&mdash;Specifies the template of the options content. The target type of this style is `Telerik.Maui.Controls.The target type of this template is Telerik.Maui.Controls.OptionsButtonToolbarItemViewContent`.

The other available properties are the properties used in the [DropDownButtonToolbarItemView]({%slug toolbar-items-dropdown-button%}#styling), [ButtonToolbarItemView]({%slug toolbar-items-button%}#styling), [ToolbarItemView]({%slug toolbar-items%}#styling) and [LabelToolbarItemView]({%slug toolbar-items-label%}#styling).

## See Also

- [SplitButton ToolbarItem]({%slug toolbar-items-split-button%})
- [ToggleButton ToolbarItem]({%slug toolbar-items-toggle-button%})
- [Label ToolbarItem]({%slug toolbar-items-label%})
- [NavigationButton ToolbarItem]({%slug toolbar-items-navigation-button%})
- [ListPicker ToolbarItem]({%slug toolbar-items-listpicker-button%})
- [Group ToolbarItem]({%slug toolbar-items-group%})
- [RadioButton ToolbarItem]({%slug toolbar-items-radio-button%})
- [Slider ToolbarItem]({%slug toolbar-items-slider%})