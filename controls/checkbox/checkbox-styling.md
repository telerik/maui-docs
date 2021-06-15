---
title: Styling
page_title: .NET MAUI CheckBox Documentation | Styling
description: Check our &quot;Styling&quot; documentation article for Telerik CheckBox for .NET MAUI control.
position: 4
slug: checkbox-styling
---

# Styling

The purpose of this help article is to show you the styling options of the **RadCheckBox** control. 

## Colors

RadCheckBox exposes a few useful Color properties for customizing its visual appearance. You could set the color of the check mark as well as the control itself in each of the available states.

 * Background/Border Colors
   * **CheckedColor**: Defines the Color applied to the control when it is checked. This is both the border and background color.
   * **UncheckedColor**: Defines the Color applied to the control when it is unchecked. This is the border color only, the background is transparent when unchecked.
   * **IndeterminateColor**: Defines the Color applied to the control when it is in Indeterminate state. This is both the border and background color.
 * Symbol Colors
   * **CheckedSymbolColor**: Defines the Color applied to the check symbol of the control when it is in Checked state.
   * **IndeterminateSymbolColor**: Defines the Color applied to the Indeterminate symbol of the control.


Here is the result at runtime with all of the above examples:

![CheckBox Color Changing Options Example](images/checkbox-colors.png)

> RadCheckBox follows the guidelines of the operating system, meaning that on iOS it is visualized as circle and on Android and WinUI - as square.

## See Also

- [CheckBox Getting Started]({% slug checkbox-getting-started%})
- [CheckBox Key Features]({% slug checkbox-key-features%})
