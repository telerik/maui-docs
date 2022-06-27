---
title: Prompt Character
page_title: .NET MAUI MaskedEntry Documentation - Prompt Character
description: "Implement prompt characters for the mask positions which have not yet been filled in by the user in the Telerik UI for .NET MAUI MaskedEntry."
position: 6
slug: maskedentry-prompt-character
---

# Prompt Character

The MaskedEntry exposes a `PromptChar`(`char`) property, which represents a symbol (char) for any mask position that the user has not filled in yet. The default `PromptChar` value is `_` (underscore).

**Setting the IPMaskedEntry**

<snippet id='ipmaskedentry-xaml' />

**Setting the TextMaskedEntry**

<snippet id='textmaskedentry-mask-xaml' />

## Customization

To change the default prompt character, set the `PromptChar`(`char`) property.

**IPMaskedEntry with PromptChar="#"**

<snippet id='ipmaskedentry-promptchar-xaml' />

**TextMaskedEntry with PromptChar=" "**

<snippet id='textmaskedentry-numbers-xaml' />

## See Also

- [Mask Types]({%slug maskedentry-masked-types%})
- [Validation]({%slug maskedentry-validation%})
- [Setting Value]({%slug maskedentry-value%})
- [Null Values Support]({%slug maskedentry-value%}#null-value-support})
- [Events]({%slug maskedentry-events%})
- [Globalization]({%slug maskedentry-globalization%})
