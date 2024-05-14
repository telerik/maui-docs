---
title: Content Configuration
page_title: .NET MAUI TemplatedButton Documentation - Content Alignment
description: Learn how to define, position, and format the content of the Telerik TemplatedButton for .NET MAUI.
position: 3
tags: .net maui, telerik templated button for .net maui, ui for .net maui, template contet, microsoft .net maui
slug: templatedbutton-configuration
---

# .NET MAUI TemplatedButton Content Configuration

The purpose of this help article is to show you the main configuration options of the control.

## Setting Content

Define the content inside the TemplatedButton by setting the `Content` property (`object`) or `ContentTemplate` (`DataTemplate`) property.

The `Content` is responsible for the actual content displayed in the button. It can be set to `string`, `View`, object, etc.

Here are the scenarios for the visualization of `Content` or `ContentTemplate` inside the `RadTemplatedButton`:

* If `ContentTemplate` is set, the `View` returned from the `ContentTemplate`.`CreateView()` is displayed inside the `RadTemplatedButton.ControlTemplate`, having `Content` as its `BindingContext`.

* If `ContentTemplate` is `DataTemplateSelector`, first the `DataTemplate` is selected and then a `View` is created from the chosen template using `Content` as its `BindingContext`.

* If `Content` is set to a `View` and `ContentTemplate` isn't set, the `View` is displayed inside the `RadTemplatedButton.ControlTemplate`.
If `Content` is set to a `string` and `ContentTemplate` isn't set, a `Label` is displayed inside the `RadTemplatedButton.ControlTemplate`.

* If `Content` is set to an `object` and `ContentTemplate` isn't set, the `ToString()` of the `object` is used and converted to `Label` inside the `RadTemplatedButton.ControlTemplate`.

__Setting Content to String__

<snippet id='templatedbutton-gettingstarted-xaml' />

![.NET MAUI TemplatedButton Getting Started](images/templatedbutton-getting-started.png)

__Setting ContentTemplate__

<snippet id='templatedbutton-content-template' />

![.NET MAUI TemplatedButton ContentTemplate](images/templatedbutton-contenttemplate.gif "TemplatedButton for .NET MAUI")

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

- [Loading Button]({%slug templatedbutton-loading-button%})
- [Set Visual States]({%slug templatedbutton-visual-states%})
- [Events]({%slug templatedbutton-events%})
- [Execute Command]({%slug templatedbutton-command%})
- [Style the TemplatedButton]({%slug templatedbutton-styling%})