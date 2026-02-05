---
title: Visual States
page_title: .NET MAUI Editor Documentation - Visual States
description: Learn how to set the border color, background color, and other visual states for the Telerik UI for .NET MAUI Editor control.
position: 9
tags: .net maui, telerik .net maui, ui for .net maui, Editor, states, microsoft .net maui
slug: editor-visual-states
---

# .NET MAUI Editor Visual States

This article describes the visual states provided by the Editor control. You can use these visual states to change the appearance of the control based on its state—such as when it’s disabled, focused, hovered, and more.

The Editor provides the following `CommonStates` visual states:

@[template](/_contentTemplates/controls/inputview.md#inputview-visual-states)

## Using the Visual States

The following example demonstrates how to use the Editor's Visual States.

**1.** Define the Editor in XAML:

<snippet id='editor-style' />

**2.** Define the Editor's style in the page's resources:

<snippet id='editor-styling' />

**3.** Define the clear button style in the page's resources:

<snippet id='editor-styling-clear-button' />

**4.** Define the validation error label style in the page's resources:

<snippet id='editor-styling-validation-error-label' />

**5.** Define the validation error image style in the page's resources:

<snippet id='editor-styling-validation-error-image' />

**6.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

This is the result on WinUI: 

![.NET MAUI Editor Visual States](images/editor-styling.gif)

>tip For a runnable example demonstrating the Editor's Visual States, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **Editor > Styling** category.

## See Also

- [Text Appearance]({%slug editor-text-appearance%})
- [Text Selection]({%slug editor-text-selection%})
- [Events]({%slug editor-events%})
- [Styling]({%slug editor-styling%})
- [Validation]({%slug editor-validation%})
