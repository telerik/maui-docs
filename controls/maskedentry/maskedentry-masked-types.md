---
title: Mask Types
page_title: .NET MAUI MaskedEntry Documentation | Mask Types
description: Check our &quot;Masked Types&quot; documentation article for Telerik MaskedEntry for .NET MAUI.
position: 2
slug: maskedentry-masked-types
---

# Mask Types

The MaskedEntry provides a number of mask types, which enable you to restrict user input to a specific type such as email, text, and more.

## Email Mask

To validate the user input as an email entry, use the `EmailMaskedEntry`. The resulting value is a string object.

To enable the email mask type, set the `RadEmailMaskedEntry` instance:

<snippet id='emailmaskedentry-xaml' />

The following image shows the end result.

![RadEmailMaskedEntry](images/maskedentry_email.png)

## Numeric Mask

To validate the user input as numeric values, use the `NumericMaskedEntry`.

The numeric mask displays the following values:

* Percent values.
* Decimal values.
* Currency (culture-aware).
* Fixed point values.

Through the `Mask` property you can specify the exact format of the expected input. The following example demonstrates how to set the `RadNumericMaskedEntry` with the `Currency` value.

<snippet id='numericmaskedentry-mask-c-xaml' />

The following image shows the end result.

![RadNumericMaskedEntry](images/maskedentry_numeric.png)

## Regex Mask

To validate the user input as a standard (alphanumeric) user input against a regular expression, use the `RegexMaskedEntry`, which provides errors if the regular expression (regex) rule is not matched. The resulting value is a string.

The following example demonstrates how to set the `RadRegexMaskedEntry`.

<snippet id='regexmaskedentry-getting-started-xaml' />

The following image shows the end result.

![RadRegexMaskedEntry](images/maskedentry_regex.png)

## IP Mask

To validate the user input as an IP Address input, use the `IPMaskedEntry`. The resulting value is a string object.

The following example demonstrates how to create a `RadIPMaskedEntry`.

<snippet id='ipmaskedentry-xaml' />

The following image shows the end result.

![RadIPMaskedEntry](images/maskedentry_ip.png)

## Text Mask

To validate the user input as text symbols, use the `TextMaskedEntry`. The resulting value is a string object.

The following example demonstrates how to create a `RadTextMaskedEntry`.

<snippet id='textmaskedentry-getting-started-xaml' />

The following image shows the end result.

![RadTextMaskedEntry](images/maskedentry_text.png)

## See Also

- [Getting Started]({%slug maskedentry-getting-started%})
- [Validation]({%slug maskedentry-validation%})
- [Null Values Support]({%slug maskedentry-value%}#null-value-support})
- [Events]({%slug maskedentry-events%})
- [Globalization]({%slug maskedentry-globalization%})
