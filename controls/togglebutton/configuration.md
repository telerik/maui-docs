---
title: Configuration
page_title: .NET MAUI ToggleButton Documentation - Content Alignment
description: Learn how to align the content of the Telerik ToggleButton for .NET MAUI horizontally or vertically.
position: 3
tags: .net maui, telerik toggle button for .net maui, ui for .net maui, toggle button, microsoft .net maui
slug: togglebutton-contenfiguration
---

# .NET MAUI ToggleButton Configuration

The purpose of this help article is to show you the main configuration options of the control.

## Setting Content

Define a content inside the ToggleButton by setting the `Content` property (`object`) or `ContentTemplate` (`DataTemplate`) property. 

Here are the scenarios in which the `Content` or `ConetentTemplate` will be visualized inside the `RadToggleButton`:

* If `Content` is set and `ContentTemplate` is set, the `View` returned from the `ContentTemplate.CreateView()` will be displayed inside the `RadToggleButton.ControlTemplate`, having `Content` as its `BindingContext`. 
* If `Content` is set to a `string` and no `ContentTemplate` is set, a `Label` with `Text` will be displayed inside the `Content`.
* If `Content` is set to a `View` and no `ContentTemplate` is set, the `View` will be displayed inside the `RadToggleButton.ControlTemplate`.
* If `Content` is set to a data object and no `ContentTemplate`is set, the `ToString()` of the data object will be used and converted to `Label` inside the `RadToggleButton.ControlTemplate`.
* If `ContentTemplate` is set, the `View` returned from the `ContentTemplate.CreateView()` will be displayed inside the `RadToggleButton.ControlTemplate`, having `Content` as its `BindingContext`. 
* If `ContentTemplate` is `DataTemplateSelector`, first the `DataTemplate` will be selected and then a `View` will be created from the chosen template using `Content` as its `BindingContext`.

__Setting Content to String__

<snippet id='togglebutton-gettingstarted-xaml' />

__Setting ContentTemplate__

<snippet id='togglebutton-content-template' />

> For a runnable example demonstrating the ToggleButton ContentTemplate, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **ToggleButton > Features** category.

## Text Alignment

Use the following properties to align the text in the button when `Content` is `string` and `ContentTemplate` is not set.

* `HorizontalTextAlignment` (`Microsoft.Maui.TextAlignment`)&mdash;Specifies the horizontal alignment of the `Label.Text`. 
* `VerticalTextAlignment` (`Microsoft.Maui.TextAlignment`)&mdash;Specifies the vertical alignment of the `Label.Text`.

## Text Decoration

Use the `TextDecorations` (`Microsoft.Maui.TextDecorations`) property to specify the text decorations of the `Label` created when `Content` is `string` and `ContentTemplate` is not set.

## Font Options

The following properties specifies the font options that apply to the content when `Content` is `string` and `ContentTemplate` is not set.

* `FontFamily` (`string`)&mdash;Specifies the font family of the `Label.Text`.
* `FontSize` (`double`)&mdash;Specifies the font size in pixels of the `Label.Text`.
* `FontAttributes` (`Microsoft.Maui.Controls.FontAttributes`)&mdash;Specifies the font attributes of the `Label.Text`.

## See Also

- [Toggle State]({%slug togglebutton-toggle-states%})
- [Apply Ripple Effect]({%slug togglebutton-ripple%})
- [Set Visual States]({%slug togglebutton-visual-states%})
- [Events]({%slug togglebutton-events%})
- [Execute Command]({%slug togglebutton-command%})
- [Style the ToggleButton]({%slug togglebutton-styling%})