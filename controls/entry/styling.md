---
title: Styling
page_title: .NET MAUI Entry Documentation | Styling
description: "Learn how to use the border styles and the font styling options of the Telerik UI for .NET MAUI Entry control."
position: 6
previous_url: /controls/entry/entry-styling
slug: entry-styling
---

# Styling

The Entry provides styling options for setting the appearance of its border and font.

## Entry Style

Style the entry using the following properties:

* `CornerRadius`(`Microsoft.Maui.CornerRadius`)
* `BackgroundColor``(`Microsoft.Maui.Graphics`)

## ClearButton Style

Style the Clear button which is displayed by default when entering text in the control using the following properties:

* `ClearButtonColor`(`Microsoft.Maui.Graphics`)&mdash;Defines the color of the Clear button.
* `HoveredClearButtonColor`(`Microsoft.Maui.Graphics`)&mdash;Defines the color of the Clear button when it is hovered. The color appears only on desktop(Windows and macOS).
* `PressedClearButtonColor`(`Microsoft.Maui.Graphics`)&mdash;Defines the color of the Clear button when it is clicked.

## Font Options

The Entry control has the following properties for defining the font options:

* `FontAttributes`
* `FontFamily`
* `FontSize`
* `FontAutoScalingEnabled`

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

## See Also

- [Text Appearance]({% slug entry-text-appearance%})
- [Text Selection]({%slug entry-text-selection %})
- [Events]({% slug entry-events%})
