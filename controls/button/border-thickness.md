---
title: Border Thickness
page_title: .NET MAUI Button Documentation | Border Thickness of .NET MAUI Button
description: "Learn how to set the thickness of the Telerik Button for .NET MAUI border."
position: 3
tags: .net maui, telerik .net maui, ui for .net maui, button, microsoft .net maui
slug: border_thickness_button
---

# Border Thickness

The Button enables you to set the width of its border.

To define the border thickness of the Button, use the `BorderThickness` property, which is of the `Microsoft.Maui.Thickness` type. Type `Thickness` allows you to define a different border on each side of the Button.

The snippet below demonstrates how to define the `BorderThickness` property.

```XAML
<telerikInput:RadButton Text="Click me!"  
                        BorderThickness="6, 2, 2, 6"
                        BorderColor="#4488F6" />
```

The following image shows the end result.

![Button Key Features Example](images/button-key-features.png)

## See Also

- [Creating a Circular Button]({%slug button-howto-create-circle-button%})
