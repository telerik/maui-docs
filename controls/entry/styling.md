---
title: Styling
page_title: .NET MAUI Entry Documentation - Styling
description: "Learn how to use the border styles and the font styling options of the Telerik UI for .NET MAUI Entry control."
position: 6
previous_url: /controls/entry/entry-styling
slug: entry-styling
---

# .NET MAUI Entry Styling

The Entry provides styling options for setting the appearance of its border and font.

## Entry Style

Style the entry using the following properties:

* `CornerRadius` (of type `Microsoft.Maui.CornerRadius`)
* `BackgroundColor` (of type `Microsoft.Maui.Graphics.Color`)
  * or `Background` (of type `Microsoft.Maui.Controls.SolidColorBrush`)
* `BorderBrush` (of type `Microsoft.Maui.Controls.SolidColorBrush`)
* `BorderThickness` (of type `Microsoft.Maui.Thickness`)
* `TextColor` (of type `Microsoft.Maui.Graphics.Color`)

For example:

```XAML
<telerik:RadEntry x:Name="MyEntry"
                  Text="Hello World"
                  TextColor="DarkRed"
                  Background="Wheat"
                  BorderBrush="DarkRed"
                  BorderThickness="4,1,1,1"
                  CornerRadius="5,7,7,5"
                  WidthRequest="150"/>
```

Produces the following result on Windows:

![](./images/entry-border-styling.png)

## Clear Button Style

Style the Clear button which is displayed by default when entering text in the control using the following properties:

* `ClearButtonColor` (of type `Microsoft.Maui.Graphics`): Defines the color of the Clear button.
* `HoveredClearButtonColor` (of type `Microsoft.Maui.Graphics`): Defines the color of the Clear button when the cursor is hovering over it. The color appears only on desktop (Windows and MacOS).
* `PressedClearButtonColor` (of type `Microsoft.Maui.Graphics`): Defines the color of the Clear button when clicked.

## Font Options

The Entry control has the following properties for defining the font options:

* `FontAttributes`
* `FontFamily`
* `FontSize`
* `FontAutoScalingEnabled`

The following example demonstrates how to apply the font options to the Entry.

```XAML
<VerticalStackLayout>
    <telerik:RadEntry Text="Normal Text" />
    <telerik:RadEntry FontSize="Large" FontAttributes="Bold" Text="Bold Text - Large" />
    <telerik:RadEntry FontSize="Medium" FontAttributes="Italic" Text="Italic Text - Medium"/>
    <telerik:RadEntry FontSize="Small" Text="Italic and Bold Text - Small"  />
    <telerik:RadEntry FontSize="Micro" Text="Micro Text" />
</VerticalStackLayout>
```

## See Also

- [Text Appearance]({% slug entry-text-appearance%})
- [Text Selection]({%slug entry-text-selection %})
- [Events]({% slug entry-events%})
