---
title: Mask
page_title: .NET MAUI MaskedEntry Documentation | Mask
description: "Try now the Telerik MaskedEntry for .NET MAUI formatting and restricting text to predefined patterns, and providing input validation and masks."
position: 3
slug: maskedentry-mask
---

# Mask

Telerik MaskedEntry for .NET MAUI exposes a `Mask`(`string`) property. The property is a string of characters that constrain user input. The `Mask` property may contain literals and special mask characters depending on the used Mask Type - numeric, text, regex.

## Mask for RadNumericMaskedEntry 

You can easily set one of the [Standard Numeric Format Specifier](https://docs.microsoft.com/en-us/dotnet/standard/base-types/standard-numeric-format-strings#standard-format-specifiers) to the `Mask` property of the RadNumericMaskedEntry. 

**Percent (double) mask:**

<snippet id='numericmaskedentry-mask-p-xaml' />

**Fixed (decimal) mask:**

<snippet id='numericmaskedentry-mask-f-xaml' />

**Fixed (decimal) mask:**

<snippet id='numericmaskedentry-mask-g-xaml' />
				
**Decimal (decimal) mask:**

<snippet id='numericmaskedentry-mask-n-xaml' />

**Standart (long) mask:**

<snippet id='numericmaskedentry-mask-d-xaml' />

**Currency (decimal) mask:**

<snippet id='numericmaskedentry-mask-c-xaml' />

## Mask for RadTextMaskedEntry

If you want to allo usesrs to enter only numbers inside the RadTextMaskedEntry you can apply the following `Mask`:

<snippet id='textmaskedentry-numbers-xaml' />

And Letters Mask: 

<snippet id='textmaskedentry-mask-xaml' />

## Mask for RadRegexMaskedEntry

You can define a input pattern of your choice and set it to the `Mask` property of the RadRegexMaskedEntry:

<snippet id='regexmaskedentry-xaml' />

## See Also
