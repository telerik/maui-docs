---
title: Text Mask
page_title: .NET MAUI MaskedEntry Documentation | Text Mask
description: "Set the mask type of the Telerik UI for .NET MAUI MaskedEntry to validate the expected user input format such as text."
position: 2
slug: maskedentry-text-mask
---

# Text Mask

To validate the user input as text symbols, use the `TextMaskedEntry`. The resulting value is a string object.

The table below describe the mask characters that can be used with `TextMaskedEntry`. The characters can be set to the `Mask` property.

| **Mask Character** | **Description** |
|----|----|
|`0`|Digit, required. This element will accept any single digit between 0 and 9.|
|`9`|Digit or space, optional.|
|`#`|Digit or space, optional. If this position is blank in the mask, it will be rendered as the character in the [PromptChar]({%slug maskedentry-prompt-character%}) property. For example, "$######.##" displays as a literal "$", accepts a numeric amount with six places and two places to the right of the decimal, i.e. $123456.56.|
|`L`|Accepts letters only.|
|`?`|Letter, optional.|
|`&`|Character, required.|
|`C`|Character, optional.|
|`A`|Alphanumeric, required. Accepts any symbol.|
|`a`|Alphanumeric, optional.|
|`.`|Decimal placeholder.|
|`,`|Thousands placeholder.|
|`:`|Time separator.|
|`/`|Date separator.|
|`$`|Currency symbol.|
|`<`|Shift down. Converts all characters that follow to lowercase.|
|`>`|Shift up. Converts all characters that follow to uppercase.|
|`\`|Disable a previous shift up or shift down.|
|`\\`|Escape. Escapes a mask character, turning it into a literal. `"\\"` is the escape sequence for a backslash.|
|All other characters|All non-mask elements will appear as themselves within `RadTextMaskedEntry`. Literals always occupy a static position in the mask at run time, and cannot be moved or deleted by the user|

## Example

The following example demonstrates how to create a `RadTextMaskedEntry`:

<snippet id='textmaskedentry-getting-started-xaml' />

And the end result:

![RadTextMaskedEntry](../images/maskedentry_text.png)

>note For the **Mask Types** example, refer to the [SDKBrowserMaui Demo Application]({%slug maui-demo-app%}).

## See Also

- [Getting Started]({%slug maskedentry-getting-started%})
- [Validation]({%slug maskedentry-validation%})
- [Null Values Support]({%slug maskedentry-value%}#null-value-support})
- [Events]({%slug maskedentry-events%})
- [Globalization]({%slug maskedentry-globalization%})
