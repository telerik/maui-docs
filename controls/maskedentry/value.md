---
title: Value
page_title: .NET MAUI MaskedEntry Documentation - Value
description: "Set predefined values in the Telerik UI for .NET MAUI MaskedEntry and learn how to enable its null value support."
position: 4
slug: maskedentry-value
---

# Value

To set a predefined value inside the MaskedEntry, define the `Value`(`string`) property. It returns the user input without the formatting characters.

**TextMaskedEntry with Value property**

Define the control:

<snippet id='textmaskedentry-value-xaml' />
```C#
this.textMaskedEntry.Value = "Test";
```

Add the namespace:

```XAML
xmlns:telerik="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
```

## Null Value Support

By default, the MaskedEntry control doesn't allow you to set `null` to its `Value` property. Instead, the `null` value in the NumericMaskedEntry is coerced to `0`. To allow `null` values, you have to set the `AllowNullValue` property to `True`.

**NumericMaskedEntry with null value support**

Define the control:

<snippet id='numericmaskedentry-allownullvalues-true-xaml' />

Add the namespace:

```XAML
xmlns:telerik="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
```

> For the MaskedEntry Value example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to MaskedEntry -> Features category.

## See Also

- [Mask Types]({%slug maskedentry-masked-types%})
- [Validation]({%slug maskedentry-validation%})
- [Events]({%slug maskedentry-events%})
- [Globalization]({%slug maskedentry-globalization%})
