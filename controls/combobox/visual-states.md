---
title: Visual States
page_title: .NET MAUI ComboBox Documentation - Visual States
description: Learn how to set the border color, background color, and other visual states for the Telerik UI for .NET MAUI ComboBox control.
position: 15
tags: .net maui, telerik .net maui, ui for .net maui, combobox, states, microsoft .net maui
slug: combobox-visual-states
---

# .NET MAUI ComboBox Visual States

This article describes the visual states provided by the ComboBox control. You can use these visual states to change the appearance of the control based on its state—such as when it’s disabled, focused, hovered, and more.

The ComboBox provides the following `CommonStates` visual states:

| Visual State | Description |
| ------------- | --------------- |
| `Normal` | Applies when the ComboBox is in its normal state. |
| `Focused` | Applied when the ComboBox receives focus (when it's editable). |
| `MouseOver` | (Windows-only) Applied when the mouse cursor is hovering over the ComboBox. |
| `PointerOver` | (MacCatalyst-only) Applied when the mouse cursor is hovering over the ComboBox. |
| `Disabled` | Applied when the ComboBox's `IsEnabled` is `False`. |

## Using the Visual States

The example below demonstrates some of the styling capabilities of the ComboBox, such as custom `ClearButtonStyle`, `TextInputStyle`, `TextColor`, `PlaceholderColor`, and others. It also shows how to switch its appearance through the .NET MAUI Visual State Manager.

The example uses the same `ViewModel` and `City` classes as the [Getting Started]({%slug combobox-getting-started%}) topic.

**1.** Add a Style that targets the `RadComboBox` to your page's resources and apply all the needed styling properties and the visual states:

<snippet id='combobox-custom-styles' />

**2.** Define the ComboBox in XAML:

<snippet id='combobox-styling-xaml'/>

Here is how the ComboBox looks when styling is applied:

![.NET MAUI ComboBox Styling](images/combobox-styling.png)

Here is how the styling is applied when the control is focused and item is selected:

![.NET MAUI ComboBox Styling on Selected Item](images/combobox-styling-focused.png)

> For the ComboBox Visual States example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to the **ComboBox > Styling** category.

## See Also

- [AutoComplete Styling]({%slug autocomplete-styling%})
