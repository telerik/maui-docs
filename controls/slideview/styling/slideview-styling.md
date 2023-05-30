---
title: SlideView Styling
page_title: .NET MAUI SlideView Documentation - SlideView Styling
description: Learn how to style and customize the .NET Maui SlideView control.
position: 12
slug: slideview-styling
---

# .NET MAUI SlideView Styling

The SlideView control exposes properties that allow you to control the appearance of the Navigation Buttons and of the Indicator.

To control the appearance of the Navigation Buttons, use the following properties:

* `NavigateToPreviousItemButtonStyle`&mdash;Defines the custom `Microsoft.Maui.Controls.Style` that is regarded when creating the `Microsoft.Maui.Style` that will be applied to the button that is linked to the SlideView's `NavigateToPreviousItemCommand`.

* `NavigateToNextItemButtonStyle`&mdash;Defines the custom `Microsoft.Maui.Controls.Style` that is regarded when creating the `Microsoft.Maui.Controls.Style` that will be applied to the button that is linked to the SlideView's `NavigateToNextItemCommand`.

To control the appearance of the SlideView Indicator, use the `IndicatorStyle` property—it defines the custom `Microsoft.Maui.Controls.Style` that is regarded when creating the `Microsoft.Maui.Controls.Style` that will be applied to the SlideViewIndicator.

### Example

The following example demonstrates how to style the control.
