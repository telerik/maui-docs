---
title: Styling
page_title: .NET MAUI Border Documentation | Styling
description: "Learn more about how to set the color and thickness of the Telerik UI for .NET MAUI Barcode."
tags: .net maui, telerik .net maui, ui for .net maui, border, microsoft .net maui
position: 40
previous_url: /controls/border/border-styling
slug: border-styling
---

# .NET MAUI Border Styling

The Border control provides options for styling its appearance and enables you to set its color and thickness.

## Border Color

To specify the color of the Border, use the `BorderColor` property. If the thickness of the Border is set to `0`, the `BorderColor` property is disabled.

## Border Thickness

To specify the width of the Border control, use its `BorderThickness` property.

`BorderThickness` is of the `Microsoft.Maui.Thickness` type and allows you to define a different border on each side of the surrounded element.

The following example demonstrates how to use the `BorderColor` and `BorderThickness` properties.

<snippet id='border-features-thickness' />

The following image shows the end result.

![Border Styling](images/border-styling.png)

## See Also

- [Configuring the Corner Radius of the Border]({% slug border-corner-radius %})
