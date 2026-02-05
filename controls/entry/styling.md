---
title: Styling
page_title: .NET MAUI Entry Documentation - Styling
description: Learn how to use the border styles and the font styling options of the Telerik UI for .NET MAUI Entry control.
position: 6
previous_url: /controls/entry/entry-styling
slug: entry-styling
---

# .NET MAUI Entry Styling

The Entry provides styling options for setting the appearance of its border and font.

Style the Entry using the following properties:

@[template](/_contentTemplates/controls/inputview.md#inputview-style)

In addition to the available styling properties, you can apply specific [Visual States]({%slug entry-visual-states%}) to the Entry control.

>tip For a runnable example demonstrating the Entry Styling options, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **Entry > Styling** category.

## Clear Button Style

@[template](/_contentTemplates/controls/inputview.md#inputview-style-clearbutton)

The following example demonstrates how to style the clear button of the Entry:

<snippet id='entry-styling-clear-button' />

>tip For a runnable example demonstrating the Entry Clear button styling options, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **Entry > Styling** category.

## Font Options

The Entry control has the following properties for defining the font options:

@[template](/_contentTemplates/controls/inputview.md#inputview-styling-font)

The following example demonstrates how to apply the font options to the Entry.

```XAML
<VerticalStackLayout>
    <telerik:RadEntry Text="Normal Text" x:Name="entry"/>
    <telerik:RadEntry Text="Bold Text - Large" FontAttributes="Bold" FontSize="Large" />
    <telerik:RadEntry Text="Italic Text - Medium" FontAttributes="Italic" FontSize="Medium"/>
    <telerik:RadEntry Text="Italic and Bold Text - Small"  FontSize="Small" x:Name="smallEntry"/>
    <telerik:RadEntry Text="Micro Text"  FontSize="Micro" />
</VerticalStackLayout>
```

## Validation Error View Style

The Entry control provides the following properties for styling the validation error view:

@[template](/_contentTemplates/controls/inputview.md#inputview-validation-style)

Here is an example of how to style the validation error label:

<snippet id='entry-styling-validation-error-label' />

And here is an example of how to style the validation error image:

<snippet id='entry-styling-validation-error-image' />

>tip For a runnable example demonstrating the Entry's Styling, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **Entry > Styling** category.

## See Also

