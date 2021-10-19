---
title: Thickness
page_title: .NET MAUI Border Documentation | Thickness
description: "Learn more about how to set the thickness of the Telerik UI for .NET MAUI Border control."
tags: .net maui, telerik .net maui, ui for .net maui, border, microsoft .net maui
position: 40
slug: thickness_border
---

# Thickness

The Telerik UI for .NET MAUI Border provides the `BorderThickness` property, which enables you to specify its width.

`BorderThickness` is of the `Microsoft.Maui.Thickness` type and allows you to define a different border on each side of the surrounded element.

The following example demonstrates how to use the `BorderColor` and `BorderThickness` properties.

```XAML
<telerikMauiControls:RadBorder BorderColor="#4488F6" BorderThickness="1, 2, 1, 2">
    <Label Text="Hello there" Margin="2" />
</telerikMauiControls:RadBorder>
```

The following image shows the end result.

![Border Key Features Example](images/border-key-features.png)

## See Also

- [Setting the Color of the Border]({% slug color_border %})
- [Configuring the Corner Radius of the Border]({% slug corner_radius_border %})
