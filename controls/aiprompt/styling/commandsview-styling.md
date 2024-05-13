---
title: Commands View Styling
page_title: .NET MAUI AIPrompt Documentation - Commands View Styling
description: Learn how to style the commands inside the commands view of the Telerik .NET MAUI AIPrompt control.
position: 2
slug: aiprompt-commandsview-styling
---

# Commands View Styling

The Commands View of the AIPrompt control provides the following customization properties:

* `CommandStyle`(`Style`)&mdash;Defines the style that is to be applied to the AIPrompt command.
* `CommandGroupStyle`(`Style`)&mdash;Defines the style that is to be applied to the `RadExpander` representing an AIPrompt command group.

The following example demonstrates how to modify the commands' appearance:

**1.** Add `Style` properties with `TargetType` set to `AIPromptCommandItemView` for each command representation and `AIPromptCommandGroupView` for a command group to the page's resources:

<snippet id='aiprompt-commandsview-style' />

**2.** Add the `RadAIPrompt` control with `CommandStyle` and `CommandGroupStyle` properties applied:

<snippet id='aiprompt-commandsview-styling-xaml' />

## See Also

- [Views]({%slug aiprompt-views-overview%})
- [Commands View]({%slug aiprompt-commands-view%})
