---
title: AIPrompt Button
page_title: .NET MAUI AIPrompt Documentation - AIPrompt Button
description: Learn more about the AIPrompt button in the Telerik UI for .NET MAUI AIPrompt control.
position: 5
slug: aiprompt-aipromptbutton
---

# AIPrompt Button

The AIPrompt component can also be displayed as a button that will show a popup with an AIPrompt when interacted with. 

To display the component as a button, create a new `RadAIPromptButton` instance and add the AIPrompt component inside it.

The `RadAIPromptButton` inherits from `RadTemplatedButton` and provides the following additional properties:

* `AIPrompt`(`RadAIPrompt`)&mdash;Defines the corresponding `RadAIPrompt` control.
* `Popup`(`RadPopup`)&mdash;Defines the corresponding `RadPopup` control.

Here is an example on how you can define an AIPrompt Button:

<snippet id='aiprompt-airpromtbutton-xaml' />

## See Also

- [AIPrompt Button Styling]({%slug aiprompt-aipromptbutton-styling%})
