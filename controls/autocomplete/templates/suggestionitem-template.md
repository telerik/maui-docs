---
title: SuggestionItem Template
page_title: .NET MAUI AutoCompleteView Documentation | SuggestionItem Template
description: Check our &quot;SuggestionItem Template&quot; documentation article for Telerik AutoComplete for .NET MAUI control.
position: 1
slug: autocomplete-suggestion-item-template
---

# Suggestion Items Customization

Whenever the default template does not fit a particular scenario you can use the `SuggestionItemTemplate`.

* `SuggestionItemTemplate`(`DataTemplate`)&mdash;Defines the template that will be used to create each of the suggestions.

## Example

Here is an example how to use the RadAutoComplete `SuggestionItemTemplate`:

**1.** Create the needed business objects, for example type City with the following properties:

<snippet id='autocomplete-client-businessobject'/>

**2.** Create a ViewModel with a collection of City objects:

<snippet id='autocomplete-clients-viewmodel'/>

**3.** The following snippet shows the `SuggestionItemTemplate`:

<snippet id='autocomplete-suggestion-item-template'/>

Here is the result:

![.NET MAUI AutoComplete SuggestionItemTemplate Example](../images/autocomplete-suggestionitem-template.png "AutoComplete SuggestionItemTemplate Example")

>important For AutoComplete SuggestionItemTemplate example refer to the [SDKBrowser Demo application]({%slug sdkbrowser-app%}).

## See Also

- [Remote Search]({%slug autocomplete-remote-search%})
- [Filtering]({%slug autocomplete-filtering%})
- [Templates]({%slug autocomplete-custom-templates%})
- [Styling]({%slug autocomplete-styling%})