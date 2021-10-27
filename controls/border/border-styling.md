---
title: Styling
page_title: .NET MAUI Border Documentation | Styling
description: "Learn more about how to set the color and thickness of the Telerik UI for .NET MAUI Barcode."
tags: .net maui, telerik .net maui, ui for .net maui, border, microsoft .net maui
position: 40
slug: border-styling
---

# Styling

The purpose of this help article is to show you the styling options of the RadBorder control. 

## Border Color

RadBorder exposes `BorderColor` property, which enables you to specify its color. If the thickness of the Border is set to `0`, the `BorderColor` property is disabled.

## Border Thickness

RadBorder provides the `BorderThickness` property, which enables you to specify its width.

`BorderThickness` is of the `Microsoft.Maui.Thickness` type and allows you to define a different border on each side of the surrounded element.

### Example

The following example demonstrates how to use the `BorderColor` and `BorderThickness` properties.

```XAML
<telerikPrimitives:RadBorder BorderColor="#4488F6" 
							 BorderThickness="1, 2, 1, 2">
    <Label Text="Hello there" Margin="2" />
</telerikPrimitives:RadBorder>
```

![Border Styling](images/border-styling.png)

## See Also

- [Configuring the Corner Radius of the Border]({% slug border-corner-radius %})