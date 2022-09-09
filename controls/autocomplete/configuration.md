---
title: Configuration
page_title: .NET MAUI AutoComplete Documentation - Configuration
description: Check our &quot;Configuration&quot; documentation article for Telerik .NET MAUI AutoComplete control.
position: 2
slug: autocomplete-configuration
---

# .NET MAUI AutoComplete Configuration

The purpose of this help article is to show you the main configuration options of the control.

## Placeholder

AutoComplete exposes `Placeholder` property which is used to give guidance to the end user on what should be entered in the text input.
You could also use the `PlaceholderColor` property to define the placeholder text color of the component.

<snippet id='autocompleteview-features-watermark'/>

## Display Mode

* `DisplayMode`(`Telerik.Maui.Controls.AutoCompleteDisplayMode`)&mdash;Determines whether a single or multiple selection is enabled. The default `DisplayMode` is `Plain`, for multiple selection you have to set it to `Tokens`.

## Completion Mode

* `CompletionMode`(`Telerik.Maui.Controls.AutoCompleteCompletionMode`)&mdash;Specifying the way the control filters its ItemsSource when typing in its input. The matching items to the filter are displayed in a SuggestionView if the RadAutoComplete.AutoCompleteSuggestMode is `Append` or `SuggestAppend`.

## Keyboard

The `Keyboard` property of type `Microsoft.Maui.Keyboard` allows you to define the type of the keyboard that will be visualized by the device. 

```XAML
<telerikInput:RadAutoCompleteView Keyboard="Numeric" />
```

## Clear button visibility

The Clear button, which appears at the right side of the input field when the AutoComplete is on focus, gives the end-user the option to quickly clear the entered values. You could control the visibility of the button through the `IsClearButtonVisible` property. The default value is `True`.

<snippet id='autocomplete-clearbutton-visibility'/>

## No results message

The NoResults message appears in the popup used for the list of suggestions whenever the control cannot find any matching items.  You could use the following properties to customize the NoResult message:

* `NoResultsMessage`(`string)`&mdash;Defines the message visualized when there are no suggestions found.
* `NoResultsTemplate`(`DataTemplate`)&mdash;Defines the template visualized when there are no suggestions found.

<snippet id='autocomplete-noresultsmessage'/>

## Search Threshold

By default the search is triggered as soon as the user types into the input field. By using `SearchThreshold` you can configure AutoComplete to trigger the search after a certain number of letters is entered. 

<snippet id='autocomplete-searchthreshold'/>

## SuggestionView visibility

* `ShowSuggestionView`(`bool`)&mdash;Determine the visibility of the popup containing the search results of the AutoComplete. The default value is `True`.
* `SuggestionViewHeight`(double`)&mdash;Defines the SuggestionViewHeight of the control.
* `SuggestionViewBackgroundColor`(`Color`)&mdash;Defines the BackgroundColor of the suggestion view.

<snippet id='autocomplete-suggestionview'/>

## SuggestionView position

* `SuggestionViewPosition` property which enables you to explicitly define whether the suggestions popup will be shown below or above the input field. `SuggestionViewPosition` is of enum type `Telerik.Maui.Controls.AutoCompletePopupPosition` and can be set to any of the following values:

* (default) `Auto`
* `Top`
* `Bottom`

Where `Auto` calculates the available space and chooses what's the best position of the popup, starting with `Bottom`. With `Top`/`Bottom` setting, the popup is positioned above or below the AutoComplete respectively.

<snippet id='autocomplete-suggestionview-position' />

## See Also

