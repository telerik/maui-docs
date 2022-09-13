---
title: Size
page_title: .NET MAUI CheckBox Documentation - Size
description: "Set the width and height of the Telerik CheckBox for .NET MAUI by adjusting only a single property."
position: 3
slug: checkbox-size
---

# Size

The CheckBox provides options for setting its height and width.

To define the dimensions of the control, use the `Length`(`double`) property, which maintains a 1:1 aspect ratio. The default value is `18`.

The following example demonstrates how to set the `Length` value.

```XAMl
<telerik:RadCheckBox x:Name="checkboxLength" Length="40" StrokeWidth="5"/>
```

The image below shows the result at runtime displaying the defined Indeterminate state together with the configured `StrokeWidth` and `Length` properties.

![CheckBox Stroke Size](images/checkbox-features.png)

## See Also

- [Defining the Checkbox State]({% slug checkbox-checked-states %})
- [Styling Options of the Checkbox]({% slug checkbox-styling%})
