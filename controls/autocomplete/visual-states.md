---
title: Visual States
page_title: .NET MAUI AutoComplete Documentation - Visual States
description: Learn how to set the border color, background color, and other visual states for the Telerik UI for .NET MAUI AutoComplete control.
position: 17
tags: .net maui, telerik .net maui, ui for .net maui, autocomplete, states, microsoft .net maui
slug: autocomplete-visual-states
---

# .NET MAUI AutoComplete Visual States

This article describes the visual states provided by the AutoComplete control. You can use these visual states to change the appearance of the control based on its state—such as when it’s disabled, focused, hovered, and more.

The AutoComplete provides the following `CommonStates` visual states:

| Visual State | Description |
| ------------- | --------------- |
| `Normal` | Applies when the AutoComplete is in its normal state. |
| `Focused` | Applied when the AutoComplete receives focus. |
| `MouseOver` | (Windows-only) Applied when the mouse cursor is hovering over the AutoComplete. |
| `PointerOver` | (MacCatalyst-only) Applied when the mouse cursor is hovering over the AutoComplete. |
| `Disabled` | Applied when the AutoComplete's `IsEnabled` is `False`. |

## Using the Visual States

The example below demonstrates some of the styling capabilities of the AutoComplete, such as custom `ClearButtonStyle`, `TextInputStyle`, `TextColor`, `PlaceholderColor`, and others. It also shows how to switch its appearance through the .NET MAUI Visual State Manager.

**1.** Add a Style that targets the `RadAutoComplete` to your page's resources and apply all the needed styling properties and the visual states:

<snippet id='autocomplete-custom-styles' />

**2.** Define the AutoComplete in XAML:

<snippet id='autocomplete-styling-xaml'/>

**3.** Create the needed business objects, for example type `Client` with the following properties:

<snippet id='autocomplete-client-businessobject'/>

**4.** Create a `ViewModel` with a collection of `Client` objects:

<snippet id='autocomplete-extended-clients-viewmodel'/>

Here is how the AutoComplete looks when styling is applied:

![.NET MAUI AutoComplete Styling](images/autocomplete-styling.png)

>tip For a runnable example demonstrating the AutoComplete's Visual States, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **AutoComplete > Styling** category.

## See Also

- [AutoComplete Styling]({%slug autocomplete-styling%})
- [Apply Implicit Style]({%slug style-combobox-autocomplete-entry-implicit-explicit%})
- [Styling AutoComplete Using Visual States]({%slug style-autocomplete-visual-state-border-telerik-maui%})
