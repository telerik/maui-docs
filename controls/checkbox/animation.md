---
title: Animation
page_title: .NET MAUI CheckBox Documentation - Animation
description: Learn how to disable the default animation in Telerik .NET MAUI Checkbox control.
position: 3
slug: checkbox-animation
---

# .NET MAUI CheckBox Animation

The CheckBox provides built-in animation when changing the state of the control&mdash;`Checked`,`Unchecked`, and `Indeterminate`.

![.NET MAUI CheckBox Built-In Animation](images/checkbox-features.png)

To remove the built-in animation, use the `IsAnimated` (`bool`) property. The default value is `true`.

The following example demonstrates how to set the `IsAnimated` property.

```XAMl
<telerik:RadCheckBox x:Name="checkboxLength" IsAnimated="False" />
```

The videos below shows how the control changes the states when the animation is disabled:

![.NET MAUI CheckBox Disabled Animation](images/checkbox-features.png)

## See Also

- [Defining the Checkbox State]({% slug checkbox-checked-states %})
- [Styling Options of the Checkbox]({% slug checkbox-styling%})
