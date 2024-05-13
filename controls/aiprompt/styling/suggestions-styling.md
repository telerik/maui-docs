---
title: Suggestions Styling
page_title: .NET MAUI AIPrompt Documentation - Suggestions Styling
description: Learn how to style the suggestions shown inside the input view of the Telerik .NET MAUI AIPrompt control.
position: 4
slug: aiprompt-suggestions-styling
---

# Suggestions Styling

The Input View of the AIPrompt control allows you to define suggestions for the user prior to initiating a request through the `Suggestions` property. You can modify the visual appearance of each suggest with the `SuggestionStyle` property:

* `SuggestionStyle`(`Style`)&mdash;Defines the style that is to be applied to the suggestions inside the input view

The following example demonstrates how to modify the suggestions' appearance:

**1.** Add a `Style` property with `TargetType` set to `AIPromptInputSuggestionView` to the page's resources:

<snippet id='aiprompt-suggestion-style'/>

**2.** Add the `RadAIPrompt` control with `SuggestionStyle` applied:

<snippet id='aiprompt-suggestion-style-xaml'/>

## See Also

- [Suggestions]({%slug aiprompt-suggestions%})
- [Views]({%slug aiprompt-views-overview%})
- [Input View]({%slug aiprompt-input-view%})
