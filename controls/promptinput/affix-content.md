---
title: Affix Content
page_title: .NET MAUI PromptInput Documentation - Affix Content
description: Learn how to add custom content around the input area of the Telerik UI for .NET MAUI PromptInput control through the top, start, and end affix content templates.
position: 6
slug: promptinput-affix-content
---

# .NET MAUI PromptInput Affix Content

The PromptInput allows you to add custom content in different regions around the input area. This is useful for scenarios such as displaying the active topic, selecting a chat model, or showing a character counter next to the input.

The affix content is configured through the following properties:

* `TopAffixContentTemplate` (`DataTemplate`)&mdash;Defines the template for the content displayed above the text input area and below the attached files view.
* `StartAffixContentTemplate` (`DataTemplate`)&mdash;Defines the template for the content displayed on the left side at the bottom of the prompt input area, after the default content, that is, the 'More' button.
* `EndAffixContentTemplate` (`DataTemplate`)&mdash;Defines the template for the content displayed on the right side at the bottom of the prompt input area, before the default content, that is, the Speech-to-Text and Send buttons.

The following example demonstrates how to add custom content in the top, start, and end affix regions of the PromptInput.

**1.** Define the top affix template, which renders a settings icon with a popup and a label for the active topic:

<snippet id='promptinput-affix-top-template' />

**2.** Define the start affix template, which renders a combo box for selecting a chat model:

<snippet id='promptinput-affix-start-template' />

**3.** Define the end affix template, which displays the current character count:

<snippet id='promptinput-affix-end-template' />

**4.** Apply the templates to the PromptInput:

<snippet id='promptinput-affix' />

**5.** Define the `ViewModel` and set it as the `BindingContext` of the page:

<snippet id='promptinput-viewmodel-affix' />

>tip For a runnable example demonstrating the PromptInput Affix Content, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **PromptInput > Features** category.

## See Also

- [Getting Started]({%slug promptinput-getting-started%})
- [Configuration]({%slug promptinput-configuration%})
- [Commands]({%slug promptinput-commands%})
- [Styling]({%slug promptinput-styling%})
