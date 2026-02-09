---
title: Styling
page_title: .NET MAUI Editor Documentation - Styling
description: Learn how to use the border styles and the font styling options of the Telerik UI for .NET MAUI Editor control.
position: 6
slug: editor-styling
---

# .NET MAUI Editor Styling

The Editor provides styling options for setting the appearance of its border and font.

Style the Editor using the following properties:

@[template](/_contentTemplates/controls/inputview.md#inputview-style)

In addition to the available styling properties, you can apply specific [Visual States]({%slug editor-visual-states%}) to the Editor control.

>tip For a runnable example demonstrating the Editor Styling options, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **Editor > Styling** category.

## Clear Button Style

@[template](/_contentTemplates/controls/inputview.md#inputview-style-clearbutton)

The following example demonstrates how to style the clear button of the Editor:

<snippet id='editor-styling-clear-button' />

>tip For a runnable example demonstrating the Editor Styling options, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **Editor > Styling** category.

## Font Options

The Editor control has the following properties for defining the font options:

@[template](/_contentTemplates/controls/inputview.md#inputview-styling-font)

The following example demonstrates how to apply the font options to the Editor.

```XAML
<VerticalStackLayout>
    <telerik:RadEditor Text="Normal Text" x:Name="entry"/>
    <telerik:RadEditor Text="Bold Text - Large" FontAttributes="Bold" FontSize="Large" />
    <telerik:RadEditor Text="Italic Text - Medium" FontAttributes="Italic" FontSize="Medium"/>
    <telerik:RadEditor Text="Italic and Bold Text - Small"  FontSize="Small" x:Name="smallEntry"/>
    <telerik:RadEditor Text="Micro Text"  FontSize="Micro" />
</VerticalStackLayout>
```

## Validation Error View Style

The Editor control provides the following properties for styling the validation error view:

@[template](/_contentTemplates/controls/inputview.md#inputview-validation-style)

Here is an example of how to style the validation error label:

<snippet id='editor-styling-validation-error-label' />

And here is an example of how to style the validation error image:

<snippet id='editor-styling-validation-error-image' />

>tip For a runnable example demonstrating the Editor's Styling, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **Editor > Styling** category.

## See Also


- [Text Appearance]({%slug editor-text-appearance%})
- [Text Selection]({%slug editor-text-selection%})
- [Events]({%slug editor-events%})
- [Validation]({%slug editor-validation%})
- [Visual States]({%slug editor-visual-states%})