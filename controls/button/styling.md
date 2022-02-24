---
title: Styling
page_title: .NET MAUI Button Documentation | Styling
description: "Learn how to set the border color and border thickness of the Telerik Button for .NET MAUI."
position: 3
tags: .net maui, telerik .net maui, ui for .net maui, button, microsoft .net maui
slug: button-styling
---

# Styling

To define the border thickness of the Button, use the `BorderThickness` property, which is of the `Microsoft.Maui.Thickness` type. Type `Thickness` allows you to define a different border on each side of the Button.

The snippet below demonstrates how to define the `BorderThickness` property.

```XAML
<telerik:RadButton Text="Click me!"  
				   BorderThickness="6, 2, 2, 6"
				   BorderColor="#4488F6" />
```


The following image shows the end result.

![Button Key Features Example](images/button-key-features.png)

## See Also

- [Creating a Circular Button]({%slug button-create-circle-button%})
