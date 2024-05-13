---
title: Styling
page_title: .NET MAUI ToggleButton Documentation - Styling
description: Learn how to set the border color, border thickness and other styling properties of the Telerik ToggleButton for .NET MAUI.
position: 11
tags: .net maui, telerik .net maui, ui for .net maui, toggle, button, microsoft .net maui
slug: togglebutton-styling
---

# .NET MAUI ToggleButton Styling

The ToggleButton provides a set of styling options by exposing properties for customizing its visual appearance.

## Styling the ToggleButton

To style the ToggleButton, use the following properties:

* `Background` (`Brush`)&mdash;Specifies the background brush of the control.
* `BackgroundColor` (`Color`)&mdash;Specifies the background color of the control.
* `BorderColor` (`Color`)&mdash;Specifies the border color of the control.
* `BorderBrush` (`Brush`)&mdash;Specifies the border brush of the control.
* `BorderThickness` (`Thickness`)&mdash;Specifies the border thickness of the control.
* `CornerRadius` (`CornerRadius`)&mdash;Specifies the corner radius of the control.
* `Padding` (`Thickness`)&mdash;Specifies the padding of the control.
* `TextColor` (`Color`)&mdash;Specifies the color of the `Label.Text` created when `Content` is `string` and `ContentTemplate` is not set.

### Using the Styling API

The following example demonstrates how to apply implicit and explicit styles to the ToggleButton.

**1.** Define the buttons in XAML:

<snippet id='togglebutton-styling' />

**2.** Define the explicit styling to the page's resources:

<snippet id='togglebutton-styling-explicit' />

**3.** Define the implicit styling to the page's resources:

<snippet id='togglebutton-styling-implicit' />

**4.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

This is the result on WinUI: 

![.NET MAUI ToggleButton Styling](images/togglebutton-styling.gif)

>tip For a runnable example demonstrating the ToggleButton styling options, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **ToggleButton > Styling** category.

## See Also

- [Configure the ToggleButton]({%slug togglebutton-configuration%})
- [Toggle State]({%slug togglebutton-toggle-states%})
- [Set Visual States]({%slug togglebutton-visual-states%})
- [Events]({%slug togglebutton-events%})
- [Execute Command]({%slug togglebutton-command%})
