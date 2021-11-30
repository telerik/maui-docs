---
title: Validation
page_title: .NET MAUI MaskedEntry Documentation | Validation
description: "Check the MaskedEntry Validation topic to learn more about the built-in validation error messages and how to define a custom error message"
position: 7
slug: maskedentry-validation
---

# Validation

Telerik MaskedEntry for .NET MAUI has a built-in validation message. If you entering an input that does not match the mask requrements an error message will be displayed.

## Default Validation Error Message

MaskedEntry has a deafult validation error message, based on the used Masked Type:

* EmailMaskedEntry&mdash;`E-Mail is not valid`.

* RegexMaskedEntry&mdash;`Input does not match the regex`.

## Custom Validation Error Message 

You can easily customize the default validation error message using the `ValidationErrorMessage`(`string`) property.

**RadEmailMaskedEntry ValidationErrorMessage**

<snippet id='emailmaskedentry-validationerrormessage-xaml' />

**RadRegexMaskedEntry ValidationErrorMessage**

<snippet id='regexmaskedentry-validationerrormessage-xaml' />

>tip ValidationErrorMessage example can be found in the MaskedEntry/Features folder of the [SDK .NET MAUI Application]({%slug maui-demo-app%}).

## See Also

- [Mask Types]({%slug maskedentry-masked-types%})
- [Setting Value]({%slug maskedentry-value%})
- [Null Values Support]({%slug maskedentry-value%}#null-value-support})
- [Prompt Character]({%slug maskedentry-prompt-character%})
- [Events]({%slug maskedentry-events%})
- [Globalization]({%slug maskedentry-globalization%})
