---
title: Styling
page_title: .NET MAUI CheckBox Documentation - Styling
description: Set the border, background, and symbol color of the Telerik UI for .NET MAUI CheckBox and customize its visual appearance.
position: 4
previous_url: /controls/checkbox/checkbox-styling
slug: checkbox-styling
---

# .NET MAUI CheckBox Styling

The CheckBox provides a set of styling options by exposing properties for customizing its visual appearance.

You can set the color of the check mark as well as the control itself in each of the available states.

## Background, Border, and Symbol Colors

To set the background and border colors of the CheckBox, use the following properties:

* `CheckedColor`&mdash;Defines the Color applied to the control when its checked. This is both the border and background color.
* `UncheckedColor`&mdash;Defines the Color applied to the control when its unchecked. This is the border color only, the background is transparent when unchecked.
* `IndeterminateColor`&mdash;Defines the Color applied to the control when its in Indeterminate state. This is both the border and background color.

To set the symbol colors of the CheckBox, use the following properties:

* `CheckedSymbolColor`&mdash;Defines the Color applied to the check symbol of the control when its in Checked state.
* `IndeterminateSymbolColor`&mdash;Defines the Color applied to the Indeterminate symbol of the control.

The following example demonstrates how to set the `CheckedColor` property.

```XAML
<telerik:RadCheckBox CheckedColor="Aqua" />
```

The following example demonstrates how to set the `UncheckedColor` property.

```XAML
<telerik:RadCheckBox UncheckedColor="DarkBlue" />
```

The following example demonstrates how to set the `CheckedSymbolColor` property.

```XAML
<telerik:RadCheckBox CheckedSymbolColor="Black" />
```

The following example demonstrates how to set the `IndeterminateColor` and `IndeterminateSymbolColor` properties.

```XAML
<telerik:RadCheckBox x:Name="checkbox" IsChecked="{x:Null}" IndeterminateColor="Brown" IndeterminateSymbolColor="Coral" />
```

The image below shows the end result.

![CheckBox Color Changing Options](images/checkbox-colors.png)

## Corner Radius

Apply corner radius to the Checkbox control using the `CornerRadius`(`double?`) property.

```XAML
<telerik:RadCheckBox x:Name="checkbox" CornerRadius="3"/>
```

## Stroke Thickness

The CheckBox exposes a `StrokeWidth`(`double`) property that specifies the width of the lines with which the Checkbox element is drawn. It affects the border of the control as well as the check mark. The default value is `2`.

The following example demonstrates how to apply a `StrokeWidth` value.

```XAMl
<telerik:RadCheckBox x:Name="checkboxStrokeWidth" StrokeWidth="5"/>
```

The image below shows the result at runtime displaying the defined Indeterminate state together with the configured `StrokeWidth` and `Length`.

![CheckBox Stroke Thickness](images/checkbox-features.png)

## Remove the Animation

The CheckBox control exposes a `IsAnimated` (`bool`) property that allows to remove the animations during state transitions. The default value is `True`.

## See Also

- [Setting the Checkbox Dimensions]({% slug checkbox-size %})
- [Defining the Checkbox State]({% slug checkbox-checked-states %})
