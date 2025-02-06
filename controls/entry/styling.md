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

* `CornerRadius` (`Microsoft.Maui.CornerRadius`)
* `BackgroundColor` (`Microsoft.Maui.Graphics.Color`)
* `TextColor` (`Microsoft.Maui.Graphics.Color`)
* `PlaceholderColor` (`Microsoft.Maui.Graphics.Color`)
* `BorderBrush` (`Microsoft.Maui.Controls.Brush`)
* `BorderThickness` (`Microsoft.Maui.Thickness`)

In addition to the available styling properties, you can apply specific [Visual States]({%slug entry-visual-states%}) to the Entry control.

>tip For a runnable example demonstrating the Entry Styling options, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **Entry > Styling** category.



## Clear Button Style

Style the Clear button which is displayed by default when entering text in the control using the following properties:

* `ClearButtonVisibility` (`enum` of type `Microsoft.Maui.ClearButtonVisibility`)&mdash;Defines a value indicating whether the clear button (the button that clears the text when pressed) will be visible. The options are: `Never` and `WhileEditing` (default).
* `ClearButtonStyle` (`Style` with target type `RadTemplatedButton`)&mdash;Specifies the style of the clear button. Review the [TemplatedButton Visual States]({%slug templatedbutton-visual-states%}) article for more details on the available visual states.

>tip For a runnable example demonstrating the Entry Styling options, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **Entry > Styling** category.

## Font Options

The Entry control has the following properties for defining the font options:

* `FontAttributes` (`enum` of type `Microsoft.Maui.Controls.FontAttributes`)
* `FontFamily` (`string`)
* `FontSize` (`double`)
* `FontAutoScalingEnabled` (`bool`)

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
- [Styling Entry in Telerik MAUI After Upgrading to Version 8.0.0 or Later]({%slug style-entry-visual-state-border-telerik-maui%})
