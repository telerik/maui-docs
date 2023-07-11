---
title: Editor Styling
page_title: .NET MAUI RichTextEditor Documentation - RichTextEditor Styling
description: Check our &quot;RichTextEditor Styling&quot; documentation article for Telerik RichTextEditor for .NET MAUI control.
position: 1
slug: richtexteditor-styling
---

# RichTextEditor Styling

The Telerik .NET MAUI RichTextEditor provides means for modifying its visual appearance, so that it matches the style of the app. 

You can take advantage of the following styling properties:

* `BorderColor`(`Color`)&mdash;Defines the border color around the editor.
* `BorderThickness`(`Thickness`)&mdash;Defines the border thickness around the editor.
* `CornerRadius`(`Thickness`)&mdash;Defines corner radius of the border.
* `BackgroundColor`(`Color`)&mdash;Defines the background color of the editor.

>important On WinUI, the `BackgroundColor` works when the color is initially applied and with colors that have Alpha = `1`. So you do not have to add transparency to the `BackgroundColor` on WinUI.

## Example

Here is a quick example how you can apply the listed properties:

<snippet id='richtexteditor-styling-xaml' />

This is the result:

![.NET MAUI RichTextEditor Styling](../images/richtexeditor-styling.png)

>important For the RichTextEditor Styling example, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **RichTextEditor > Styling**.

## See Also

- [RichTextEditor Toolbar Styling]({%slug richtexteditor-toolbar-styling%})
- [Custom Toolbar]({%slug richtexteditor-custom-toolbar%})
