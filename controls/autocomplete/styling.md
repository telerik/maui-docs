---
title: Styling
page_title: .NET MAUI AutoComplete Documentation - Styling
description: Change the Telerik .NET MAUI AutoComplete look using its flexible styling API.
position: 16
slug: autocomplete-styling
---

# .NET MAUI AutoComplete Styling

The Telerik UI for .NET MAUI AutoComplete control provides the following Style properties for customizing its look:

* `TextColor`(`Color`)&mdash;Defines the text color of the control.
* `PlaceholderColor`(`Color`)&mdash;Defines the color for the placeholder text.
* `Font Options`(`FontAttributes`, `FontFamily`, `FontSize`)&mdash;Defines the font options for the text of the AutoComplete.
* `BorderBrush`(`Brush`)&mdash;Defines the brush of the border around the control.
* `BorderThickness`(`Thickness`)&mdash;Defines the thickness of the border around the control.
* `ClearButtonStyle` (of type `Style` with target type `Telerik.Maui.Controls.RadTemplatedButton`)&mdash;Defines the style for the clear button.

The AutoComplete control uses the [`RadTextInput`]({%slug entry-textinput%}) control internally. To style the input control (`RadTextInput`), use the `TextInputStyle` (of type `Style` with target type `Telerik.Maui.Controls.RadTextInput`).

In addition to the available styling properties, you can apply specific [Visual States]({%slug autocomplete-visual-states%}) to the AutoComplete control.

## Suggestion View Styling 

The following properties style the AutoComplete SuggestionView (the dropdown with the suggestions):

* `SuggestionViewBackgroundColor`(`Color`)&mdash;Defines the background color of the SuggestionView.
* `SuggestionViewBorderColor`(`Color`)&mdash;Defines the color of the SuggestionView border.
* `SuggestionViewBorderThickness`&mdash;Defines the thickness of the border that surrounds the SuggestionView.
* `SuggestionViewCornerRadius`&mdash;Defines the corner radius applied to the SuggestionView.
* `SuggestionItemHighlightTextColor`&mdash;Defines the highlight color of the selection items.

### Example for AutoComplete Styling

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

And when an item is selected:

![.NET MAUI AutoComplete Styling Selected Item](images/autocomplete-selected-styling.png)

>tip For a runnable example demonstrating the AutoComplete's Styling options, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **AutoComplete > Styling** category.

## Highlight Customization

In case a custom template is used, the user can achieve text highlighting inside the `RadAutoComplete.SuggestionItemTemplate` using `RadHighlightLabel`.

The AutoComplete `RadHighlightLabel` exposes the following properties:

* `HighlightTextColor`
* `HighlightText`
* `UnformattedText`

Here is an example with `RadHighlightLabel`:

**1.** Create the needed business objects, for example type Client with the following properties:

<snippet id='autocomplete-client-businessobject'/>

**2.** Create a ViewModel with a collection of Client objects:

<snippet id='autocomplete-clients-viewmodel'/>

**3.** Use the following snippet to declare a RadAutoComplete in XAML with `RadHighlightLabel`:

<snippet id='autocomplete-highlight-text-behavior'/>

Here is the result:

![AutoComplete Highlight Customization](images/autocomplete-highlight.png "AutoComplete Highlight Customization")

>important For AutoComplete HighlightText example, refer to the [SDKBrowser Demo application]({%slug sdkbrowser-app%}) and go to the **AutoComplete > Featrues** category.

## See Also

- [Apply Implicit Style]({%slug style-combobox-autocomplete-entry-implicit-explicit%})
- [Styling the AutoComplete Using Visual States]({%slug style-autocomplete-visual-state-border-telerik-maui%})
- [Data Binding]({%slug autocomplete-data-binding%})
- [Configuration]({%slug autocomplete-configuration%})
- [Suggest Mode]({%slug autocomplete-suggest-mode%})
- [Display Text]({%slug autocomplete-display-text-formatter%})
- [Tokens Support]({%slug autocomplete-tokens-support%})
- [Filtering]({%slug autocomplete-filtering%})
- [Templates]({%slug autocomplete-custom-templates%})
