---
title: Configuration
page_title: .NET MAUI AutoComplete Documentation - Configuration
description: Learn what are the options to configure the Telerik UI AutoComplete for .NET MAUI.
position: 3
slug: autocomplete-configuration
---

# .NET MAUI AutoComplete Configuration

The purpose of this help article is to show you the main configuration options of the control.

## Placeholder

AutoComplete exposes `Placeholder` property which is used to give guidance to the end user on what should be entered in the text input.
You can also use the `PlaceholderColor` property to define the placeholder text color of the component.

<snippet id='autocomplete-placeholder'/>

## Display Mode

* `DisplayMode` (`Telerik.Maui.Controls.AutoCompleteDisplayMode`)&mdash;Specifies how an item picked from the `SuggestionView` is visualized. 

The default `DisplayMode` is `Plain`&mdash;The picked item is visualized as plain text. If you want to visualize multiple items, set the `DisplayMode` to `Tokens`&mdash;Each item is displayed in a Token box.

## Completion Mode

The Telerik UI for .NET MAUI AutoComplete control filters the source by the entered text. By using the `CompletionMode` (enum of type `Telerik.Maui.Controls.AutoCompleteCompletionMode`) property, you can specify how the `ItemsSource` will be filtered when the user types in the input area:

* `StartsWith` filters the items that start with the text typed in the input area.
* `Contains` filters the items that contain the text typed in the input area.

The matching items to the filter are displayed in a `SuggestionView` if the `RadAutoComplete.AutoCompleteSuggestMode` is `Append` or `SuggestAppend`.

## Keyboard

The `Keyboard` property of type `Microsoft.Maui.Keyboard` allows you to define the type of the keyboard that will be visualized by the device. 

```XAML
<telerikInput:RadAutoComplete Keyboard="Numeric" />
```

## Clear Button Visibility

The Clear Button, which appears at the right side of the input field when the AutoComplete is on focus, gives the end-user the option to quickly clear the entered values. You can control the visibility of the button through the `IsClearButtonVisible` property. The default value is `True`.

<snippet id='autocomplete-clearbutton-visibility'/>

## No Results Message

The `NoResults` message appears in the popup used for the list of suggestions whenever the control cannot find any matching items.  You can use the following properties to customize the `NoResult` message:

* `NoResultsMessage` (`string)`&mdash;Defines the message visualized when no suggestions are found.
* `NoResultsTemplate` (`DataTemplate`)&mdash;Defines the template visualized when no suggestions are found.

<snippet id='autocomplete-noresultsmessage'/>

## Search Threshold

By default the search is triggered as soon as the user types into the input field. By using `SearchThreshold` you can configure AutoComplete to trigger the search after a certain number of letters is entered. 

<snippet id='autocomplete-searchthreshold'/>

## Highlight Item Behavior

When filtering is performed and there are matching items, the items are displayed in the `SuggestionView`. 

By default, the first item in the `SuggestionView` is highlighted. To modify this behavior use the `HighlightItemFunc` (`Func<IEnumerable<object>, string, object>`) property. The function receives the filtered collection of items and the current search text as parameters and returns the item from the filtered collection that should be highlighted.

@[template](/_contentTemplates/controls/autocomplete.md#highlighted-behavior)

## SuggestionView Visibility

* `ShowSuggestionView` (`bool`)&mdash;Determine the visibility of the popup containing the search results of the AutoComplete. The default value is `True`.
* `SuggestionViewHeight` (`double`)&mdash;Defines the height of the `SuggestionView`.
* `SuggestionViewMaxHeight` (`double`)&mdash;Defines the max height of the `SuggestionView`. Always set the `SuggestionViewMaxHeight`, so that you can have a predefined height for the suggestion view. If using both the `SuggestionViewMaxHeight` and `SuggestionViewHeight` properties, the max height value must be higher.
* `SuggestionViewBorderColor` (`Color`)&mdash;Defines the color of the suggestion view border (drop-down).
* `SuggestionViewBorderThickness` (`Thickness`)&mdash;Defines the thickness of the border around the suggestion view.
* `SuggestionViewCornerRadius` (`Thickness`)&mdash;Defines the corner radius applied to the suggestion view.
* `SuggestionViewBackgroundColor` (`Color`)&mdash;Defines the `BackgroundColor` of the suggestion view.

<snippet id='autocomplete-suggestionview'/>

## SuggestionView Position

* `SuggestionViewPosition` property which enables you to explicitly define whether the suggestions popup will be shown below or above the input field. `SuggestionViewPosition` is of enum type `Telerik.Maui.Controls.AutoCompletePopupPosition` and can be set to any of the following values:

	* (default) `Auto`
	* `Top`
	* `Bottom`

Where `Auto` calculates the available space and chooses what's the best position of the popup, starting with `Bottom`. With `Top`/`Bottom` setting, the popup is positioned above or below the AutoComplete respectively.

<snippet id='autocomplete-suggestionview-position' />

## See Also

- [Remote Search]({%slug autocomplete-remote-search%})
- [Suggest Mode]({%slug autocomplete-suggest-mode%})
- [Filtering]({%slug autocomplete-filtering%})
- [Events]({%slug autocomplete-events%})
- [Methods]({%slug autocomplete-methods%})
- [Templates]({%slug autocomplete-custom-templates%})
- [Styling]({%slug autocomplete-styling%})
