---
title: Dimensions
page_title: .NET MAUI CheckBox Documentation | Key Features
description: "Set the width and height of the Telerik CheckBox for .NET MAUI by adjusting only a single property."
position: 3
slug: checkbox_dimensions
---

# Dimensions

The CheckBox provides options for setting its height and width.

To define the dimensions of the control, use the `Length` property, which maintains a 1:1 aspect ratio.

The following example demonstrates how to set the `Length` value.

```XAMl
<telerikPrimitives:RadCheckBox x:Name="checkboxLength" Length="40" StrokeWidth="5"/>
```

The image below shows the result at runtime displaying the defined Indeterminate state together with the configured `StrokeWidth` and `Length` properties.

![CheckBox Key Feature Example](images/checkbox-features.png)

## See Also

- [Defining the Checkbox State]({% slug checkbox_states %})
- [Styling Options of the Checkbox]({% slug checkbox-styling%})
