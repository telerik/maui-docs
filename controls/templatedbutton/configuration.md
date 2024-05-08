---
title: Configuration
page_title: .NET MAUI TemplatedButton Documentation - Content Alignment
description: Learn how to align the content of the Telerik TemplatedButton for .NET MAUI horizontally or vertically.
position: 2
tags: .net maui, telerik templated button for .net maui, ui for .net maui, template contet, microsoft .net maui
slug: templatedbutton-contenfiguration
---

# .NET MAUI TemplatedButton Configuration

The purpose of this help article is to show you the main configuration options of the control.

## Setting Content

Define a content inside the TemplatedButton by setting the `Content` property (`object`) or `ContentTemplate` (`DataTemplate`) property. 

Here are the scenarios in which the `Content` or `ConetentTemplate` will be visualized inside the `RadTemplatedButton`:

If `Content` and `ContentTemplate` are set, the `View` returned from the `ContentTemplate.CreateView()` will be displayed inside the `RadTemplatedButton.ControlTemplate`, having `Content` as its `BindingContext`. 
If `Content` is set to a `string` and `ContentTemplate` isn't set, a `Label` with `Text` will be displayed inside the `Content`.
If `Content` is set to a `View` and `ContentTemplate` isn't set, the `View` will be displayed inside the `RadTemplatedButton.ControlTemplate`.
If `Content` is set to a data object and `ContentTemplate` isn't set, the `ToString()` of the data object will be used and converted to `Label` inside the `RadTemplatedButton.ControlTemplate`.
If `ContentTemplate` is set, the `View` returned from the `ContentTemplate.CreateView()` will be displayed inside the `RadTemplatedButton.ControlTemplate`, having `Content` as its `BindingContext`. 
If `ContentTemplate` is `DataTemplateSelector`, first the `DataTemplate` will be selected and then a `View` will be created from the chosen template using `Content` as its `BindingContext`.

## Text Alignment

Use the following properties to align the text in the button when `Content` is `string` and `ContentTemplate` is not set.

* `HorizontalTextAlignment` (`Microsoft.Maui.TextAlignment`)&mdash;Specifies the horizontal alignment of the `Label.Text`. 
* `VerticalTextAlignment` (`Microsoft.Maui.TextAlignment`)&mdash;Specifies the vertical alignment of the `Label.Text`.

## Text Decoration

Use the `TextDecorations` (`Microsoft.Maui.TextDecorations`) property to specify the text decorations of the `Label` created when `Content` is `string` and `ContentTemplate` is not set.

## Font Options

The following porperties specifies the font options that apply to the content when `Content` is `string` and `ContentTemplate` is not set.

* `FontFamily` (`string`)&mdash;Specifies the font family of the `Label.Text`.
* `FontSize` (`double`)&mdash;Specifies the font size in pixels of the `Label.Text`.
* `FontAttributes` (`Microsoft.Maui.Controls.FontAttributes`)&mdash;Specifies the font attributes of the `Label.Text`.

## See Also
