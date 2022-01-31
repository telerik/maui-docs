---
title: Regex Mask
page_title: .NET MAUI MaskedEntry Documentation | Regex Mask
description: "Set the mask type of the Telerik UI for .NET MAUI MaskedEntry to validate the expected user input format such as regex."
position: 4
slug: maskedentry-regex-mask
---

# Regex Mask

To validate the user input as a standard (alphanumeric) user input against a regular expression, use the `RegexMaskedEntry`, which provides errors if the regular expression (regex) rule is not matched. The resulting value is a string.

|**Regex** | **Usage** |
|---|---|
|`"[0-9]"` | a single digit|
|`"[0-9]{1}"` | a single digit (required)|
|`"[a-zA-Z]"` | a single letter|
|`"[a-zA-Z]{1}"` | a single letter (required)|
|`"\S"` | all symbols without space|
|`"."` | all symbols|
|`"[0-9a-zA-Z]"` | all without special symbols and space|
|`"[0-9a-zA-Z ]"` | all without special symbols|

## Example

The following example demonstrates how to set the `RadRegexMaskedEntry`:

<snippet id='regexmaskedentry-getting-started-xaml' />

And the end result:

![RadRegexMaskedEntry](../images/maskedentry_regex.png)

>note For the **Mask Types** example, refer to the [SDKBrowserMaui Demo Application]({%slug maui-demo-app%}).

## See Also

- [Getting Started]({%slug maskedentry-getting-started%})
- [Validation]({%slug maskedentry-validation%})
- [Null Values Support]({%slug maskedentry-value%}#null-value-support})
- [Events]({%slug maskedentry-events%})
- [Globalization]({%slug maskedentry-globalization%})
