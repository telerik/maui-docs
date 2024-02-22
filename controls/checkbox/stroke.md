---
title: Stroke
page_title: .NET MAUI CheckBox Documentation - Stroke
description: Set the stroke thickness to the Telerik CheckBox for .NET MAUI by adjusting only a single property.
position: 3
slug: checkbox-stroke
---

# .NET MAUI CheckBox Stroke Width

The CheckBox provides options for setting width of the lines with which the Checkbox element is drawn.

To define the width of the lines use the `StrokeWidth` (`double`) property. This property affects the border of the control as well as the check mark. The default value is `2`.

The following example demonstrates how to set the `StrokeWidth` value.

```XAMl
<telerik:RadCheckBox x:Name="checkboxStrokeWidth" StrokeWidth="5"/>
```

The image below shows the result at runtime displaying the defined Indeterminate state together with the configured `StrokeWidth`.

![.NET MAUI CheckBox Stroke Width](images/checkbox-features.png)

## See Also

- [Defining the Checkbox State]({% slug checkbox-checked-states %})
- [Styling Options of the Checkbox]({% slug checkbox-styling%})
