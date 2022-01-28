---
title: Mask Types
page_title: .NET MAUI MaskedEntry Documentation | Mask Types
description: "Set the mask type of the Telerik UI for .NET MAUI MaskedEntry to validate the expected user input format such as email, numbers, ip, regex, text."
position: 1
slug: maskedentry-masked-types
---

# Mask Types

The MaskedEntry provides separate masked entry controls wich can handle different types of user input. They all inherit from a common `RadMaskedEntryBase` class.

The available masks and their purpose are listed below:

* [Text]({%slug maskedentry-text-mask%})&mdash;Used for handling all types of text user input. The `Value` property is a `string`.
* [Numeric]({%slug maskedentry-numeric-mask%})&mdash;Used for handling numeric user input. The `Value` property can be `double` or `decimal`.
* [Regex]({%slug maskedentry-regex-mask%})&mdash;Used for handling and validating a standard (alphanumeric) user input against a regular expression. Provides errors if the regex is not matched. The `Value` property is a `string`.
* [IP]({%slug maskedentry-ip-mask%})&mdash;Used for handling and validating an IP Address input. The `Value` property is `string`.
* [Email]({&slug maskedentry-email-mask&})&mdash;Used for handling and validating an email input. The Value property is string.

>important The `Value` can also be `null` for all mask types.

>note For the **Mask Types** example, refer to the [SDKBrowserMaui Demo Application]({%slug maui-demo-app%}).

## See Also

- [Getting Started]({%slug maskedentry-getting-started%})
- [Validation]({%slug maskedentry-validation%})
- [Null Values Support]({%slug maskedentry-value%}#null-value-support})
- [Events]({%slug maskedentry-events%})
- [Globalization]({%slug maskedentry-globalization%})
