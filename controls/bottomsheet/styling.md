---
title: Styling
page_title: .NET MAUI BottomSheet Documentation - Styling
description: Learn more about how to style the handle in the Telerik UI for .NET MAUI BottomSheet.
position: 15
slug: bottomsheet-styling
---

# .NET MAUI BottomSheet Styling

The Telerik UI for .NET MAUI BottomSheet control provides the following Style properties for customizing its look:

* `BackgroundColor` (`Color`)&mdash;Specifies the background color of the control.
* `BorderColor` (`Color`)&mdash;Specifies the border color around the control.
* `BorderBrush` (`Brush`)&mdash;Specifies the border brush around the control.
* `BorderThickness` (`Thickness`)&mdash;Specifies the border thickness around the control.
* `CornerRadius` (`Thickness`)&mdash;Specifies the corner radius of the border around the control.

Here is an example of the BottomSheet styling.

**1.** Define the BottomSheet in XAML:

<snippet id='bottomsheet-style' />

**2.** Define the `RadBottomSheet` style in page's resources:

<snippet id='bottomsheet-style-resource' />

**3.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

> For a runnable example with the BottomSheet Style scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **BottomSheet > Styling** category.

## Handle Styling

You can style the handle by setting the `HandleStyle` property to the `RadBottomSheet`. The target type of the `HandleStyle` is `BottomSheetHandle`.

The available properties are described below:

* `BackgroundColor` (`Color`)&mdash;Specifies the background color of the control.
* `BorderColor` (`Color`)&mdash;Specifies the border color around the control.
* `BorderBrush` (`Brush`)&mdash;Specifies the border brush around the control.
* `BorderThickness` (`Thickness`)&mdash;Specifies the border thickness around the control.
* `CornerRadius` (`Thickness`)&mdash;Specifies the corner radius of the border around the control.
* `WidthRequest` (`double`)&mdash;Specifies the width of the handle.
* `HeightRequest` (`double`)&mdash;Specifies the height of the handle.

Here is an example of the BottomSheet handle styling.

**1.** Define the BottomSheet in XAML:

<snippet id='bottomsheet-handle-style' />

**2.** Define the `BottomSheetHandle` style in page's resources:

<snippet id='bottomsheet-handle-style-resource' />

**3.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```
> For a runnable example with the BottomSheet Handle Style scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **BottomSheet > Styling** category.

## See Also

- [Configure the BottomSheet]({%slug bottomsheet-configuration%})
- [Animation when opening and closing the bottom sheet]({%slug bottomsheet-animation%})
- [Events]({%slug bottomsheet-events%})
- [Methods]({%slug bottomsheet-methods%})