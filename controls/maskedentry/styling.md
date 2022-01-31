---
title: Styling
page_title: .NET MAUI MaskedEntry Documentation | Styling
description: "Explore the Styling API of the MaskedEntry control."
position: 11
slug: maskedentry-styling
---

# Styling

This article explains all styling options you can apply to the MaskedEntry control. The properties are valid for all mask types.

The `MaskedEntryBase` class exposes the following properties: 

* `TextColor`(`Microsoft.Maui.Graphics`)&mdash;Defines the color of the text inside the masked entry.
* `EntryCornerRadius`(`Microsoft.Maui`)&mdash;Defines the corner radius around the masked entry 
* `EntryBackgroundColor`(`Microsoft.Maui.Graphics`)&mdash;Defnes the bacground color of the masked entry
* `BackgroundColor`(`Microsoft.Maui.Graphics`)&mdash;Defines the background color of the masked control.
* `ClearButtonColor`(`Microsoft.Maui.Graphics`)&mdash;Defines the color of the clear button.
* `HoveredClearButtonColor`(`Microsoft.Maui.Graphics`)&mdash;Defines the color of the clear button when it is hovered. The color appears only on desktop.
* `PressedClearButtonColor`(`Microsoft.Maui.Graphics`)&mdash;Defines the color of the clear button when it is pressed.

## Example

We will style the `EmailMaskedEntry`. Here is the XAML definition:

<snippet id='maskedentry-styling-xaml' />

Add the namespace:

```XAML
xmlns:telerik="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
```


**ClearButtonColor**

![maskedentry-styling](images/maskedentry-clear-button-color.png)

**PressedClearButtonColor**

![maskedentry-styling](images/maskedentry-pressed-clear-button-color.png)

**HoveredClearButtonColor**

![maskedentry-styling](images/maskedentry-hovered-clear-button-color.png)

>tip For the **Styling** example, refer to the **MaskedEntry/Features** folder of the [SDK .NET MAUI Application]({%slug maui-demo-app%}).

## See Also

- [Mask Types]({%slug maskedentry-masked-types%})
- [Validation]({%slug maskedentry-validation%})
- [Events]({%slug maskedentry-events%})
- [Globalization]({%slug maskedentry-globalization%})
