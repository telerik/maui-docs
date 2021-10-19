---
title: Corner Radius
page_title: .NET MAUI Border Documentation | Corner Radius
description: "Learn more about how to define the corner radius of the Telerik UI for .NET MAUI Border control."
tags: .net maui, telerik .net maui, ui for .net maui, border, microsoft .net maui
position: 30
slug: corner_radius_border
---

# Corner Radius

The Telerik UI for .NET MAUI Border provides the `BorderColor` property, which enables you to specify its color.

If the thickness of the Border is set to `0`, the `BorderColor` property is disabled.

The following figure demonstrates how to set the color of the Border control.  

![Border Key Features Example](images/border-key-features.png)



The following figure demonstrates how to set the corner radius of the Border control.  

![Border Key Features Example](images/border-key-features.png)


The **CornerRadius** property represents the degree to which the corners of the Border are rounded. CornerRadius is of type *Microsoft.Maui.Thickness* so it allows you to set separate values on the four corners of the border.

```XAML
<telerikMauiControls:RadBorder BorderColor="#4488F6"
							   BorderThickness="1"
							   CornerRadius="15, 5, 15, 5">
    <Label Text="Hello there" Margin="2" />
</telerikMauiControls:RadBorder>
```

Additionally, the wrapped content will be clipped according to each side’s specified corner radius. The next example shows how you could have circle image by wrapping Image control with RadBorder.

```XAML
<telerikMauiControls:RadBorder CornerRadius="25"
							   BorderThickness="2"
							   BorderColor="CornflowerBlue">
    <Image Source="XamarinIcon.png"
		   WidthRequest="50"
		   HeightRequest="50" />
</telerikMauiControls:RadBorder>
```

Here is the end result:

#### Telerik Border for .NET MAUI

![Border Key Features Example](images/border-key-features.png)

## See Also

- [Getting Started]({% slug maui-getting-started%})
