---
title: Value
page_title: .NET MAUI MaskedEntry Documentation | Value
description: "Check the Telerik MaskedEntry for .NET MAUI Value article for details how to set predefined values inside the control"
position: 4
slug: maskedentry-value
---

# Value

If you want to have a prefedfined values inside the MAskedEntry, set the `Value`(`string`) property. It returns the user input without the formatting characters. 

**Example with RadTextMaskedEntry with Value property**

<snippet id='textmaskedentry-value-xaml' />
```C#
this.textMaskedEntry.Value = "Test";
```

And the namespace used:

```XAML
xmlns:telerik="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
```

## Null Value Support

By default the MaskedEntry control doesn't allow you to set `null` to its `Value` property. Instead `null` in the NumericMaskedEntry the value is coerced to `0`. To allow null values you have to set the `AllowNullValue` property to `True`.

**Example for Null Value with RadNumericMaskedEntry**

<snippet id='numericmaskedentry-allownullvalues-true-xaml' />

And the namespace used:

```XAML
xmlns:telerik="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
```

>tip AllowNullValues example can be found in the MaskedEntry/Features folder of the [SDK MAUI Application]({%slug maui-demo-app%}).

## See Also

- [Mask Types]({%slug maskedentry-masked-types%})
- [Validation]({%slug maskedentry-validation%})
- [Events]({%slug maskedentry-events%})
- [Globalization]({%slug maskedentry-globalization%})