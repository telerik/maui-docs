---
title: Styling
page_title: .NET MAUI MaskedEntry Documentation - Styling
description: "Explore the Styling API of the MaskedEntry control."
position: 11
slug: maskedentry-styling
---

# Styling

The MaskedEntry control delivers a set of options for styling its appearance.

The `MaskedEntryBase` class exposes the following properties, which are valid for all mask types.:

* `TextColor`(`Microsoft.Maui.Graphics`)&mdash;Defines the color of the text inside the MaskedEntry.
* `EntryCornerRadius`(`Microsoft.Maui`)&mdash;Defines the corner radius around the MaskedEntry.
* `EntryBackgroundColor`(`Microsoft.Maui.Graphics`)&mdash;Defines the background color of the MaskedEntry.
* `BackgroundColor`(`Microsoft.Maui.Graphics`)&mdash;Defines the background color of the masked control.
* `ClearButtonColor`(`Microsoft.Maui.Graphics`)&mdash;Defines the color of the **Clear** button.
* `HoveredClearButtonColor`(`Microsoft.Maui.Graphics`)&mdash;Defines the color of the **Clear** button when it is hovered. The color appears only on desktop.
* `PressedClearButtonColor`(`Microsoft.Maui.Graphics`)&mdash;Defines the color of the **Clear** button when it is clicked.

The following example demonstrates how to style the `EmailMaskedEntry`. Define the control in XAML:

<snippet id='maskedentry-styling-xaml' />

Add the namespace:

```XAML
xmlns:telerik="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
```


**ClearButtonColor**

![MaskedEntry ClearButton Color](images/maskedentry-clear-button-color.png)

**PressedClearButtonColor**

![MaskedEntry Pressed ClearButton Color](images/maskedentry-pressed-clear-button-color.png)

**HoveredClearButtonColor**

![MaskedEntry Hovered ClearButton Color](images/maskedentry-hovered-clear-button-color.png)

> For the MaskedEntry Styling example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to MaskedEntry -> Features category.


## See Also

- [Mask Types]({%slug maskedentry-masked-types%})
- [Validation]({%slug maskedentry-validation%})
- [Events]({%slug maskedentry-events%})
- [Globalization]({%slug maskedentry-globalization%})
