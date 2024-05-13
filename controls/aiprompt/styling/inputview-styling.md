---
title: Input View Styling
page_title: .NET MAUI AIPrompt Documentation - Input View Styling
description: Learn how to style the editor and the input button inside the input view of the Telerik .NET MAUI AIPrompt control.
position: 1
slug: aiprompt-inputview-styling
---

# Input View Styling

The Input View of the AIPrompt control provides the following customization properties:

* `InputEditorStyle`(`Style`)&mdash;Defines the style that is to be applied to the input editor.
* `InputButtonStyle`(`Style`)&mdash;Defines he style that is to be applied to the input button for generating the AI response.

The following example demonstrates how to modify the editor and the input button appearance:

**1.** Add `Style` properties with `TargetType` set to `Editor` for the input editor and `RadTemplatedButton` for the input button to the page's resources:

<snippet id='aiprompt-inputview-style'/>

**2.** Add the `RadAIPrompt` control with `TabViewStyle` applied:

<snippet id='aiprompt-inputview-styling-xaml'/>

## See Also

- [Views]({%slug aiprompt-views-overview%})
- [Input View]({%slug aiprompt-input-view%})
