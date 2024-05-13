---
title: Content Configuration
page_title: .NET MAUI ToggleButton Documentation - Content Alignment
description: Learn how to define, position, and format the content of the Telerik ToggleButton for .NET MAUI.
position: 3
tags: .net maui, telerik toggle button for .net maui, ui for .net maui, toggle button, microsoft .net maui
slug: togglebutton-configuration
---

# .NET MAUI ToggleButton Content Configuration

The purpose of this help article is to show you the main configuration options of the control.

## Setting Content

Define the content inside the ToggleButton by setting the `Content` property (`object`) or `ContentTemplate` (`DataTemplate`) property.

The `Content` is responsible for the actual content displayed in the button. It can be set to `string`, `View`, complex object, etc.

The table below lists the scenarios for the visualization of `Content` or `ContentTemplate` inside the `RadToggleButton`:

| `Content` | `ContentTemplate` | Rsults |
| --------- | ----------------- | -------|
| set | set | The `View` returned from the `ContentTemplate.CreateView()` is displayed inside the `RadToggleButton.ControlTemplate`, having `Content` as its `BindingContext`. |
| set to `string` | not set | A `Label` with `Text` is displayed inside the `Content`. |
| set to `View` | not set | The `View` is displayed inside the `RadToggleButton.ControlTemplate`. |
| set to `complex object` | not set | The `ToString()` of the data object is used and converted to `Label` inside the `RadToggleButton.ControlTemplate`. |
| set to `complex object` | not set | The `View` is displayed inside the `RadToggleButton.ControlTemplate`. |
| not set | set | The `View` returned from the `ContentTemplate.CreateView()` is displayed inside the `RadToggleButton.ControlTemplate`. |
| not set | `DataTemplateSelector` | First the `DataTemplate` is selected and then a `View` is created from the chosen template using `Content` as its `BindingContext`. |

__Setting Content to String__

<snippet id='togglebutton-gettingstarted-xaml' />

![.NET MAUI ToggleButton Content](images/togglebutton-content.png "ToggleButton for .NET MAUI")

__Setting ContentTemplate__

<snippet id='togglebutton-content-template' />

![.NET MAUI ToggleButton ContentTemplate](images/togglebutton-content-template.gif "ToggleButton for .NET MAUI")

> For a runnable example demonstrating the ToggleButton ContentTemplate, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **ToggleButton > Features** category.

## Text Alignment

Use the following properties to align the text in the button when `Content` is `string` and `ContentTemplate` is not set.

* `HorizontalTextAlignment` (`Microsoft.Maui.TextAlignment`)&mdash;Specifies the horizontal alignment of the `Label.Text`. 
* `VerticalTextAlignment` (`Microsoft.Maui.TextAlignment`)&mdash;Specifies the vertical alignment of the `Label.Text`.

## Text Decoration

Use the `TextDecorations` (enum of type `Microsoft.Maui.TextDecorations`) property to specify the text decorations of the `Label` created when `Content` is `string` and `ContentTemplate` is not set.

## Font Options

The following properties specify the font options that apply to the content when `Content` is `string` and `ContentTemplate` is not set.

* `FontFamily` (`string`)&mdash;Specifies the font family of the `Label.Text`.
* `FontSize` (`double`)&mdash;Specifies the font size in pixels of the `Label.Text`.
* `FontAttributes` (`Microsoft.Maui.Controls.FontAttributes`)&mdash;Specifies the font attributes of the `Label.Text`.

## See Also

- [Toggle State]({%slug togglebutton-toggle-states%})
- [Set Visual States]({%slug togglebutton-visual-states%})
- [Events]({%slug togglebutton-events%})
- [Execute Command]({%slug togglebutton-command%})
- [Style the ToggleButton]({%slug togglebutton-styling%})