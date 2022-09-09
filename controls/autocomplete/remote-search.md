---
title: Remote Search
page_title: .NET MAUI AutoCompleteView Documentation - Remote Search
description: "Implement remote searching in the AutoComplete for .NET MAUI control."
position: 10
slug: autocomplete-remote-search
---

# .NET MAUI AutoComplete Remote Search

The Remote Search functionality of the AutoComplete control allows you to easily take the user input, trigger custom searching algorithm and assign the results to the ItemSource of the control.

* `LoadingTemplate`(`DataTemplate`)&mdash;Defines the loading message.

Implement your custom searching algorithm inside the body of the `TextChanged` event handler. 

## Example

Here is an example how the RadAutoCompleteView Remote Search works:

**1.** Create the needed business objects, for example type Client with the following properties:

<snippet id='autocomplete-client-businessobject'/>

**2.** Create a ViewModel with a collection of Client objects:

<snippet id='autocomplete-clients-viewmodel'/>

**3.** Use the following snippet to declare a RadAutoComplete in XAML:

<snippet id='autocompleteview-features-remote-search'/>

**4.** Create a custom searching algorithm and assign the result to the control's ItemsSource inside the TextChanged event handler: 

<snippet id='autocomplete-remote-search-alorithm'/>

This is the result when LoadingTemplate is searching for results: 

![.NET MAUI AutoComplete Remote Search Searching](images/autocompleteview-remote-search-searching.png "AutoComplete Remote Search Searching")

This is the search complete results:

![.NET MAUI AutoComplete Remote Search Results](images/autocompleteview-remote-search-results.png "AutoComplete Remote Search Results")

>important For the AutoComplete Remote Search example  refer to the [SDKBrowser Demo application]({%slug sdkbrowser-app%}).

## See Also


