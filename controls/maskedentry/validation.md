---
title: Validation
page_title: .NET MAUI MaskedEntry Documentation | Validation
description: "Try now the Telerik MaskedEntry for .NET MAUI formatting and restricting text to predefined patterns, and providing input validation and masks."
position: 7
slug: maskedentry-validation
---

# Validation

Telerik MaskedEntry for .NET MAUI has a built-in validation mechanisum. If you entering an input that does not match the mask requrements an error message will be displayed.

Default Validation Error Messages:

* EmailMaskedEntry&mdash;E-Mail is not valid.
* RegexMaskedEntry&mdash;Input does not match the regex.

You can easily customize the default validation error message using the `ValidationErrorMessage`(`string`) property.

**Email MaskedEntry Validation Error Message**

<snippet id='emailmaskedentry-validationerrormessage-xaml' />

**Regex MaskedEntry Validation Error Message**

<snippet id='regexmaskedentry-validationerrormessage-xaml' />

## See Also


