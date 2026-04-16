---
title: Configuration
meta_title: .NET MAUI SmartPasteButton Documentation - Provider, Text, Icon, and Template Configuration
description: Learn how to configure the Telerik SmartPasteButton for .NET MAUI by setting its provider, customizing its text and icon, and defining a custom control template.
position: 4
tags: .net maui, telerik .net maui, ui for .net maui, smartpastebutton, microsoft .net maui
slug: smartpastebutton-configuration
---

# .NET MAUI SmartPasteButton Provider, Text, Icon, and Template Configuration

The SmartPasteButton control provides configuration options for setting the smart paste provider, customizing the button text and icon, and adjusting its control template.

## Setting Provider

The `Provider` property specifies the smart paste provider that supplies fields and handles value assignment for the smart paste operation. Typically, this would be set to a container view (like a `Form` or `Layout`) that implements `Telerik.Maui.Controls.SmartPasteButton.ISmartPasteButtonProvider`.

By default, the SmartPasteButton has a built-in integration with the DataForm control. When the SmartPasteButton's `Provider` property references the DataForm instance, it allows the SmartPasteButton to extract structured information from the clipboard content and populate the corresponding fields in the DataForm based on the form structure.

## Setting Text

The `Text` property of the SmartPasteButton allows you to set the button's display text. 

To customize the appearance of the text, you can use the following properties:

- `TextColor` (`Color`)&mdash;Specifies the color of the text.
- `TextDecoration` (`TextDecorations`)&mdash;Specifies the text decorations (underline, strikethrough, or both) applied to the text.
- `FontFamily` (`string`)&mdash;Specifies the font family of the text.
- `FontSize` (`double`)&mdash;Specifies the size of the text.
- `FontAttributes` (`FontAttributes`)&mdash;Specifies the font attributes (bold, italic, or both) applied to the text.

## Setting Icon

The `IconText` property allows you to set an icon to the button's icon element.

To configure the appearance of the icon, you can use the following properties:

- `IconTextColor` (`Color`)&mdash;Specifies the color of the icon.
- `IconFontFamily` (`string`)&mdash;Specifies the font family of the icon.
- `IconFontSize` (`double`)&mdash;Specifies the size of the icon.
- `IconFontAttributes` (`FontAttributes`)&mdash;Specifies the font attributes (bold, italic, or both) applied to the icon.

## Customizing Control Template

The SmartPasteButton control template consists of a `Border` element that contains a `StackLayout` with two children: a `Label` for the icon and a `Label` for the text.

You can customize the control template to change the layout or add additional elements as needed.

This is an example of how to define a custom control template for the SmartPasteButton:

<snippet id='smartpastebutton-template-xaml' />

And the result:

![.NET MAUI SmartPasteButton Control Template](images/smartpastebutton-template.png)

> For a runnable example demonstrating the SmartPasteButton styling options, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **SmartPasteButton > Template** category.

## See Also

- [Styling the SmartPasteButton]({%slug smartpastebutton-styling%})
- [Visual States of the SmartPasteButton]({%slug smartpastebutton-visual-states%})
- [Events of the SmartPasteButton]({%slug smartpastebutton-events%})
- [Commanding with the SmartPasteButton]({%slug smartpastebutton-command%})
