---
title: Key Features
page_title: .NET MAUI Border Documentation | Key Features for .NET MAUI Border
description: Check our &quot;Key Features&quot; documentation article for Telerik Border for .NET MAUI.
tags: .net maui, telerik .net maui, ui for .net maui, border, microsoft .net maui
position: 2
slug: border-key-features
---

# Key Features

The purpose of this help article is to show you the key features of the **RadBorder** control. 

## Define RadBorder

Add RadBorder definition in XAML:

```XAML
<telerikMauiControls:RadBorder BorderColor="Red" BorderThickness="1">
    <Label Text="Hello there" Margin="2" />
</telerikMauiControls:RadBorder>
```

Add the following namespace: 

```XAML
xmlns:telerikMauiControls="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
```

## Border Color

You can use the **BorderColor** property to specify the color of RadBorder. The property has no effect if BorderThickness is set to “0”.

## Border Thickness

The **BorderThickness** property is of type *Microsoft.Maui.Thickness* and is used to set the borders’ width. Type Thickness gives you the option to define different border on each side of the surrounded element.

Here is a quick example on how to use BorderColor and BorderThickness properties:

```XAML
<telerikMauiControls:RadBorder BorderColor="#4488F6" BorderThickness="1, 2, 1, 2">
    <Label Text="Hello there" Margin="2" />
</telerikMauiControls:RadBorder>
```

## Different Corners

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
							   BorderColor="Red">
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
