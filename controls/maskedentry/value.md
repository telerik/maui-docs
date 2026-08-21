---
title: Value
page_title: .NET MAUI MaskedEntry Documentation - Value
description: Set predefined values in the Telerik UI for .NET MAUI MaskedEntry and learn how to enable its null value support.
components: ["maskedentry"]
position: 4
slug: maskedentry-value
---

# .NET MAUI MaskedEntry Value

All MaskedEntry types expose a `Value` property that gets or sets the current input without the formatting characters. 

| Masked Type | `Value` Type |
|------------|------------|
| `RadTextMaskedEntry` | `string` |
| `RadEmailMaskedEntry` | `string` |
| `RadRegexMaskedEntry` | `string` |
| `RadIPMaskedEntry` | `string` |
| `RadNumericMaskedEntry` | `object` |

The value of the `Value` property accepts null, if the `AllowNullValue` property is set to `true`. 

>caption Example with `RadTextMaskedEntry`

Define the `RadTextMaskedEntry` in XAML:

<snippet id='textmaskedentry-value-xaml' />

Add the `telerik` namespace:

```XAML
xmlns:telerik="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
```

Define the `RadTextMaskedEntry` in C#:

```C#
var mask = new RadTextMaskedEntry
{
    Value = "Test"
};
```

Add the `telerik` namespace:

```C#
using Telerik.Maui.Controls;
```

## Null Value Support

By default, the MaskedEntry control doesn't allow you to set `null` to its `Value` property. Instead, the `null` value in the NumericMaskedEntry is coerced to `0`. To allow `null` values, set the `AllowNullValue` property to `true`.

>caption `RadNumericMaskedEntry` with null value support

Define the control:

<snippet id='numericmaskedentry-allownullvalues-true-xaml' />

Add the namespace:

```XAML
xmlns:telerik="clr-namespace:Telerik.Maui.Controls;assembly=Telerik.Maui.Controls"
```

> For the MaskedEntry Value example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to **MaskedEntry > Features** category.

## See Also

- [Mask Types]({%slug maskedentry-masked-types%})
- [Validation]({%slug maskedentry-validation%})
- [Events]({%slug maskedentry-events%})
- [Globalization]({%slug maskedentry-globalization%})
