---
title: Corner Radius
page_title: .NET MAUI Border Documentation | Corner Radius
description: Learn more about how to define the corner radius of the Telerik UI for .NET MAUI Border control.
tags: .net maui, telerik .net maui, ui for .net maui, border, microsoft .net maui
position: 30
previous_url: /controls/border/border-corner-radius
slug: border-corner-radius
---

# .NET MAUI Border Corner Radius

Telerik UI for .NET MAUI Border enables you to set a different corner radius to its angles through the `CornerRadius` property.

The `CornerRadius` property represents the degree to which the corners of the Border are rounded. `CornerRadius` is of the `Microsoft.Maui.Thickness` type.

<snippet id='border-corner-radius' />

The following image shows the result from that implementation.

![Border CornerRadius](images/border_corner_radius.png)

Additionally, the wrapped content will be clipped according to the specified corner radius of each side. 

The example below demonstrates how to render a circle image by wrapping an Image control in a Border.

Let's use the following Image:

![Border Clip Sample image](images/person_01.png)

<snippet id='border-corner-radius-clipped' />

Here is the result:

![Border Circular Image](images/border_corner_radius_clipped.png)

## See Also

- [Setting the Color of the Border]({%slug border-styling %})
- [Setting the Border Thickness]({%slug border-styling %})
