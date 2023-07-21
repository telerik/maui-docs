---
title: Content Alignment
page_title: .NET MAUI Button Documentation - Content Alignment
description: Learn how to align the content of the Telerik Button for .NET MAUI horizontally or vertically.
position: 2
tags: .net maui, telerik .net maui, ui for .net maui, button, microsoft .net maui
slug: button-content-alignment
---

# Content Alignment in .NET MAUI Button

The Button enables you to set the positioning of its content.

To define a specific position of the Button content, set the `HorizontalContentAlignment` and `VerticalContentAlignment` properties of the Button, which are of the `Microsoft.Maui.TextAlignment` type.

The following example demonstrates how to use the properties.

```XAML
<telerik:RadButton Text="Click me!"  
                   BorderColor="#4488F6"
                   HorizontalContentAlignment="End"
                   VerticalContentAlignment="Start" />
```


The following image shows the end result.

![Button Content Alignment](images/button-key-features.png)

## See Also

- [Creating a Circular Button]({%slug button-create-circle-button%})
