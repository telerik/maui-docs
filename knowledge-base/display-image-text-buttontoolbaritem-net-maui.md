---
title: Displaying Image and Text in a Toolbar Item
description: Learn how to display both images and text in the button items of the Toolbar for .NET MAUI.
type: how-to
page_title: How to Display Image and Text in the ButtonToolbarItem of the Toolbar for .NET MAUI
slug: display-image-text-buttontoolbaritem-net-maui
tags: toolbar, buttontoolbaritem, image, text, display options, style, maui
res_type: kb
---

## Environment
| Property | Value |
| --- | --- |
| Product | Toolbar for .NET MAUI |
| Version | 6.2.0 |

## Description

How can I add both an image and some textual content to the buttons of the Toolbar for .NET MAUI?

## Solution

To display both an image and text in the Toolbar's `ButtonToolbarItem`, use a style with the `DisplayOptions` property set to a bitwise combination of `Text` and `Image` enum members. This allows you to enable both options simultaneously.

1. Define a style for the `ButtonToolbarItemView` target type.
2. Set the `DisplayOptions` property of the style to `"Text, Image"`.
3. Optionally, set the `ImagePosition` property to specify the position of the image relative to the text in the toolbar item.

Here is an example of how to define the style in XAML:

```xaml
<Style TargetType="telerik:ButtonToolbarItemView">
    <Setter Property="DisplayOptions" Value="Text, Image"/>
    <Setter Property="ImagePosition" Value="Right"/>
</Style>
```

For more examples, you refer to the [.NET MAUI Toolbar configuration examples](https://github.com/telerik/maui-samples/blob/main/Samples/SdkBrowser/Examples/ToolbarControl/ConfigurationCategory/ConfigurationExample/Configuration.xaml).

## Notes
- The `DisplayOptions` property supports a bitwise combination of enum members to enable multiple options.
- The `ImagePosition` property allows you to specify the position of the image relative to the text.

## See Also
- [Toolbar for .NET MAUI Documentation: ButtonToolbarItem](https://docs.telerik.com/devtools/maui/controls/toolbar/items/button)
