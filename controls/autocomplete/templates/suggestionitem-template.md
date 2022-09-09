---
title: SuggestionItem Template
page_title: Xamarin AutoCompleteView Documentation | SuggestionItem Template
description: Check our &quot;SuggestionItem Template&quot; documentation article for Telerik AutoCompleteView for Xamarin control.
position: 3
slug: autocomplete-suggestion-item-template
---

# Suggestion Items Customization

Whenever the default template does not fit a particular scenario you can use the `SuggestionItemTemplate`.

* `SuggestionItemTemplate`(`DataTemplate`)&mdash;Defines the template that will be used to create each of the suggestions.

## Example

Here is an example how to use the RadAutoCompleteView SuggestionItemTemplate:

**1.** Create the needed business objects, for example type City with the following properties:

<snippet id='autocomplete-client-businessobject'/>

**2.** Create a ViewModel with a collection of City objects:

<snippet id='autocomplete-clients-viewmodel'/>

**3.** The following snippet shows the SuggestionItemTemplate:

<snippet id='autocomplete-suggestion-item-template'/>

Here is the result:

![.NET MAUI AutoComplete SuggestionItemTemplate Example](images/autocompleteview-suggestionitem-template.png "AutoComplete SuggestionItemTemplate Example")

>important For autocomplete SuggestionItemTemplate example refer to the [SDKBrowser Demo application]({%slug sdkbrowser-app%}).

## See Also

