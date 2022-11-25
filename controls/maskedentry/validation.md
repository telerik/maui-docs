---
title: Validation Message
page_title: .NET MAUI MaskedEntry Documentation - Validation Message
description: "Learn more about the built-in validation error messages and how to define a custom error message in the Telerik UI for .NET MAUI MaskedEntry."
position: 7
slug: maskedentry-validation
---

# .NET MAUI MaskedEntry Validation Message

The Telerik MaskedEntry for .NET MAUI provides a built-in validation message. If the user is entering an input that does not match the mask requirements, the MaskedEntry will display an error message.

## Default Error Message

The MaskedEntry supports a default validation error message that is based on the used masked type:

* `EmailMaskedEntry`&mdash;Supports the `E-Mail is not valid` error message.

* `RegexMaskedEntry`&mdash;Supports the `Input does not match the regex` error message.

## Custom Error Message

To customize the default validation error message, use the `ValidationErrorMessage`(`string`) property.

**Custom Validation Error Message for the EmailMaskedEntry**

<snippet id='emailmaskedentry-validationerrormessage-xaml' />

**Custom Validation Error Message for the RegexMaskedEntry**

<snippet id='regexmaskedentry-validationerrormessage-xaml' />

> For the MaskedEntry Validation Error Message example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to MaskedEntry -> Features category.


## See Also

- [Mask Types]({%slug maskedentry-masked-types%})
- [Setting Value]({%slug maskedentry-value%})
- [Null Values Support]({%slug maskedentry-value%}#null-value-support})
- [Prompt Character]({%slug maskedentry-prompt-character%})
- [Events]({%slug maskedentry-events%})
- [Globalization]({%slug maskedentry-globalization%})
