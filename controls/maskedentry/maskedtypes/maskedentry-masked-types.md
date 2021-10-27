---
title: Overview
page_title: .NET MAUI MaskedEntry Documentation | Masked Types
description: Check our &quot;Masked Types&quot; documentation article for Telerik MaskedEntry for .NET MAUI.
position: 0
slug: maskedentry-masked-types
---

# Overview

Check below the available mask types that MaskedEntry offers and their purpose.

## Email Mask

EmailMaskedEntry control is used for handling and validating an email input. Resulting value is string object.

Create a `RadEmailMaskedEntry` instance like this:

```XAML
<telerik:RadEmailMaskedEntry x:Name="emailMaskedEntry" />
```

![RadEmailMaskedEntry](../images/maskedentry_email.png)

## Numeric Mask

NumericMaskedEntry is used for handling numeric user input.  The numeric mask is used when you need to display:

* Percent values.
* Decimal values.
* Currency (culture-aware).
* Fixed point values.
* Percent values.

Through the `Mask` property you can specify the exact format of the expected input. Here is an example of `RadNumericMaskedEntry` with "Currency" value:

```XAML
<telerik:RadNumericMaskedEntry x:Name="numericMaskedEntry" Mask="C" />
```

![RadNumericMaskedEntry](../images/maskedentry_numeric.png)

## Regex Mask

RegexMaskedEntry is used for handling and validating a standard (alphanumeric) user input against a regular expression. Provides errors if regex is not matched. Resulting value is a string.

Check a simple example of `RadRegexMaskedEntry` below:

```XAML
<telerik:RadRegexMaskedEntry x:Name="regexMaskedEntry" Mask="^[a-z]$" PlaceholderText="^[a-z]$" />
```

![RadRegexMaskedEntry](../images/maskedentry_regex.png)

## IP Mask

IPMaskedEntry is used for handling and validating an IP Address input. Resulting value is string object.

Create a `RadIPMaskedEntry` like this:

```XAML
<telerik:RadIPMaskedEntry x:Name="ipMaskedEntry" />
```

![RadIPMaskedEntry](../images/maskedentry_ip.png)

## Text Mask

TextMaskedEntry is used for for handling standard (alphanumeric) user input. Resulting value is string object.

Create a `RadTextMaskedEntry` like this:

```XAML
<telerik:RadTextMaskedEntry x:Name="textMaskedEntry" Mask="aaaaaaaaaaaaaaaaaaaa" />```

![RadTextMaskedEntry](../images/maskedentry_text.png)

## See Also

- [Getting Started]({%slug maskedentry-getting-started%})
- [Events]({%slug maskedentry-getting-started%})

