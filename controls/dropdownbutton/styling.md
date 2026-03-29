---
title: Styling
page_title: .NET MAUI DropDownButton Documentation - Styling
description: Learn how to set the border color, border thickness and other styling properties of the Telerik DropDownButton for .NET MAUI.
position: 11
tags: .net maui, telerik .net maui, ui for .net maui, dropdown, button, microsoft .net maui
slug: dropdownbutton-styling
---

# .NET MAUI DropDownButton Styling

The DropDownButton provides a set of styling options by exposing properties for customizing its visual appearance.

## Styling the DropDownButton

To style the DropDownButton, you can use the following properties:

* `Background` (`Brush`)&mdash;Specifies the background brush of the control.
* `BorderBrush` (`Brush`)&mdash;Specifies the border brush of the control.
* `BorderColor` (`Color`)&mdash;Specifies the border color of the control.
* `BorderThickness` (`Thickness`)&mdash;Specifies the border thickness of the control.
* `CornerRadius` (`CornerRadius`)&mdash;Specifies the corner radius of the control.
* `Padding` (`Thickness`)&mdash;Specifies the padding of the control.
* `TextColor` (`Color`)&mdash;Specifies the color of the `Label.Text` created when `Content` is `string` and `ContentTemplate` is not set.
* All Properties from the [Content Configuration]({%slug dropdownbutton-configuration%}) article can be applied through style.

The DropDownButton uses the .NET MAUI Visual State Manager and defines a visual state group named `CommonStates` with the following visual states:

* `Normal`
* `PointerOver`
* `Pressed`
* `Disabled`

### Using the Styling API

The following example demonstrates how to apply implicit and explicit styles to the DropDownButton using the visual states.

## See Also

- [Configure the DropDownButton]({%slug dropdownbutton-configuration%})
- [Loading Button]({%slug dropdownbutton-loading-button%})
- [Set Visual States]({%slug dropdownbutton-visual-states%})
- [Events]({%slug dropdownbutton-events%})
- [Execute Command]({%slug dropdownbutton-command%})
