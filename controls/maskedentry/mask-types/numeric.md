---
title: Numeric Mask
page_title: .NET MAUI MaskedEntry Documentation - Numeric Mask
description: Set the mask type of the Telerik UI for .NET MAUI MaskedEntry to validate the expected user input format such as numbers.
position: 3
slug: maskedentry-numeric-mask
---

# .NET MAUI Numeric Mask

To validate the user input as numeric values, use the `NumericMaskedEntry`.

The numeric mask displays the following values:

* Percent values.
* Decimal values.
* Currency (culture-aware).
* Fixed point values.

Through the `Mask` property you can specify the exact format of the expected input. The following table lists the supported formats and the resulting type of the value with each format:

| Mask | Numeric Type | Resulting .NET Type |
| ------ | ------ | ------ |
| `"C"` or `"c"` | Currency | `decimal` |
| `"D"` or `"d"` | Standard | `long (int64)` |
| `"F"` or `"f"` | Fixed-point | `decimal` |
| `"G"` or `"g"` | Fixed-point | `decimal` |
| `"N"` or `"n"` | Decimal | `decimal` |
| `"P"` or `"p"` | Percent | `double` |
| `Other` | Decimal | `decimal` |

For the full list of supported masks (except for the `"E"` and `"X"` ones), refer to the [Standard Numeric masks](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-numeric-format-strings) MSDN article.

The following example demonstrates how to set the `RadNumericMaskedEntry` with the `Currency` value:

<snippet id='numericmaskedentry-mask-c-xaml' />

The image below shows the end result.

![.NET MAUI NumericMaskedEntry](../images/maskedentry_numeric.png)

> For the MaskedEntry Numeric Mask examples, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to MaskedEntry -> Mask Types category.

## See Also

- [Getting Started]({%slug maskedentry-getting-started%})
- [Validation]({%slug maskedentry-validation%})
- [Null Values Support]({%slug maskedentry-value%}#null-value-support})
- [Events]({%slug maskedentry-events%})
- [Globalization]({%slug maskedentry-globalization%})
