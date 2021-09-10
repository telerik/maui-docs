---
title: Configuration
page_title: .NET MAUI NumericInput Documentation | Configuration
description: Check our &quot;Configuration&quot; documentation article for Telerik NumericInput for .NET MAUI
position: 2
slug: numericinput-configuration
---

# Configuration options 

This article will explain all configuration options that NumericInput control provides.

## Numeric Value

* **Value**(*double?*) property allows you to set a predefined value that will be presented by the control.

### Example

## Null Value Support

The **Value** property is of type nullable double, which enables the NumericInput control to accept null value as well.

### Example


## Input Range

You can restrinct the input using the `Minimum` and `Maximum` properties:

* **Minimum**(*double*): The minimum value that can be insert in the numeric input.
* **Maximum**(*double*): The maximum value that can be insert in the numeric input.

### Example

## Step for Increment and Decrement value 

The **Step** property defines the value step that will be applied to the input value upon each decrease/increase action. The default step is 1.

### Example


## See Also

- [Globalization]({%slug numericinput-globalization%})
- [Commands]({%slug numericinput-commands%})
