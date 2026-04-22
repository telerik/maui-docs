---
title: Styling
page_title: .NET MAUI PromptInput Documentation - Styling
description: Learn how to style the built-in buttons of the Telerik UI for .NET MAUI PromptInput control through the exposed style properties.
position: 10
slug: promptinput-styling
---

# .NET MAUI PromptInput Styling

The PromptInput provides styling options for setting the appearance of its input text and built-in buttons. 

## Styling the Prompt Text

The PromptInput exposes the following properties for customizing the appearance of the text displayed in the input area:

* `TextColor` (`Color`)&mdash;Defines the color of the text typed in the input area. The default value is `#000000`.
* `PlaceholderColor` (`Color`)&mdash;Defines the color of the placeholder (watermark) text displayed when the input area is empty.

## Styling the Buttons

Style the PromptInput buttons using the following properties:

* `SendButtonStyle` (`Style` with target type of `RadTemplatedButton`)&mdash;Defines the style applied to the Send button.
* `MoreButtonStyle` (`Style` with target type of `RadDropDownButton`)&mdash;Defines the style applied to the 'More' button.
* `SpeechToTextButtonStyle` (`Style` with target type of `RadSpeechToTextButton`)&mdash;Defines the style applied to the Speech-to-Text button.

>tip For a runnable example demonstrating the PromptInput Styling options, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **PromptInput > Styling** category.

## See Also

- [Getting Started]({%slug promptinput-getting-started%})
- [Configuration]({%slug promptinput-configuration%})
- [Commands]({%slug promptinput-commands%})
- [Affix Content]({%slug promptinput-affix-content%})
