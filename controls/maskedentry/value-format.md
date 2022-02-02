---
title: Value Format
page_title: .NET MAUI MaskedEntry Documentation | Value Format
description: "Use the ValueFormat option to control the value of the Telerik UI for .NET MAUI MaskedEntry when its Mask property is set."
position: 5
slug: maskedentry-value-format
---

# Value Format

The Telerik MaskedEntry for .NET MAUI allows you to set the behavior of the `Value` property in a mask scenario (when the `Mask` property is set). By default, the `Value` holds the characters without including the prompt characters and the literals defined in the mask.

If the `ValueFormat` property is set, the `Value` can hold both literals and prompt characters.

The `ValueFormat` property is an enum of type `Telerik.Maui.MaskedEntry.ValueFormat` and supports the following options:

* (Default mode) `ExcludePromptAndLiterals`
* `IncludePrompt`
* `IncludeLiterals`
* `IncludePromptAndLiterals`


## ExcludePromptAndLiterals

`ExcludePromptAndLiterals` is the default mode. The MaskedEntry value is stored without the prompt characters or literals defined in the mask.

For example, if `Mask="##-##"` and you enter `22-2_`, the `Value` property will contain `222`.

<snippet id='textmaskedentry-excludepromptandliterals-xaml' />

## IncludePrompt

The `Value` property of the MaskedEntry control contains the prompt characters for the missing positions required by the `Mask` property.

For example, if `Mask="##-##"` and you enter `222`, the `Value` property will be `222_`, where the `_` character is the default placeholder.

<snippet id='textmaskedentry-includelprompt-xaml' />

## IncludeLiterals

The `Value` MaskedEntry property contains the literals defined in the `Mask` property.

For example, if `Mask="##-##"` and you enter `22-2_`, the `Value` will be `22-2`, where the `-` character is the literal from the mask.

<snippet id='textmaskedentry-includeliterals-xaml' />

## IncludePromptAndLiterals

The `Value` MaskedEntry property contains both the literals and prompt characters for the missing positions required by the `Mask` property.

For example, if `Mask="##-##"` and you enter `222,` the `Value` property will be `22-2_`.

<snippet id='textmaskedentry-includelpromptandliterals-xaml' />

>tip For the **Value Format** example, refer to the **MaskedEntry/Features** folder of the [SDK .NET MAUI Application]({%slug maui-demo-app%}).

## See Also

- [Mask Types]({%slug maskedentry-masked-types%})
- [Validation]({%slug maskedentry-validation%})
- [Setting Value]({%slug maskedentry-value%})
- [Null Values Support]({%slug maskedentry-value%}#null-value-support})
- [Events]({%slug maskedentry-events%})
- [Globalization]({%slug maskedentry-globalization%})
