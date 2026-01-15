---
title: Setting the Mask
page_title: .NET MAUI MaskedEntry Documentation - Setting the Mask
description: Learn how to restrict user input by using the Mask property of the Telerik UI for .NET MAUI MaskedEntry.
position: 4
slug: maskedentry-mask
---

# Setting the Mask in .NET MAUI MaskedEntry

The Telerik MaskedEntry for .NET MAUI exposes a `Mask`(`string`) property, which represents a string of characters restricting user input. The `Mask` property can contain literals and special mask characters depending on the used mask type (numeric, text, or regex).

## Mask for the NumericMaskedEntry

You can set one of the [Standard Numeric Format Specifiers](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-numeric-format-strings#standard-format-specifiers) to the `Mask` property of the `RadNumericMaskedEntry`.

This example shows how to set the Percent (double) Mask

<snippet id='numericmaskedentry-mask-p-xaml' />

This example shows how to set the Fixed (decimal) Mask

<snippet id='numericmaskedentry-mask-f-xaml' />

This example shows how to set the Fixed (decimal) Mask

<snippet id='numericmaskedentry-mask-g-xaml' />

This example shows how to set the Decimal (decimal) Mask

<snippet id='numericmaskedentry-mask-n-xaml' />

This example shows how to set the Standard (long) Mask

<snippet id='numericmaskedentry-mask-d-xaml' />

This example shows how to set the Currency (decimal) Mask

<snippet id='numericmaskedentry-mask-c-xaml' />

## Mask for the TextMaskedEntry

To allow users to enter only numbers inside the `RadTextMaskedEntry`, apply the `Mask` for numeric restriction:

<snippet id='textmaskedentry-numbers-xaml' />

To allow users to enter only literals inside the `RadTextMaskedEntry`, apply the `Mask` for letter characters restriction:

<snippet id='textmaskedentry-mask-xaml' />

## Mask for RegexMaskedEntry

You can define an input pattern of your choice and set it to the `Mask` property of the `RadRegexMaskedEntry`:

<snippet id='regexmaskedentry-xaml' />

> For the MaskedEntry Mask Types examples, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to MaskedEntry -> Mask Types category.

## See Also

- [Mask Types]({%slug maskedentry-masked-types%})
- [Value Format]({%slug maskedentry-value-format%})
- [Validation]({%slug maskedentry-validation%})
- [Setting Value]({%slug maskedentry-value%})
- [Null Values Support]({%slug maskedentry-value%}#null-value-support})
- [Events]({%slug maskedentry-events%})
- [Globalization]({%slug maskedentry-globalization%})
