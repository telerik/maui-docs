---
title: Suggest Mode
page_title: .NET MAUI AutoCompleteView Documentation | Suggest Mode
description: Check our &quot;Suggest Mode&quot; documentation article for Telerik AutoCompleteView for Xamarin control.
position: 4
slug: autocomplete-suggest-mode
---

# Suggest Modes in .NET MAUI AutoComplete

AutoComplete exposes three different modes for providing suggestions:

* `Suggest`&mdash;Provides a drop-down list of options for you to pick from;
* `Append`&mdash;Provides an inline display of the first suggestion;
* `SuggestAppend`&mdash;Combines the functionality of the two options above, shows a drop-down with suggestions and at the same time selects the first one from the list. 

In order to choose any of those modes use the `SuggestMode` property of the control. The default `SuggestMode` is `Suggest`. 

## Example

Here is an example how the AutoComplete Suggest Mode functionality works:

Create the needed business objects, for example type Client with the following properties:

<snippet id='autocomplete-client-businessobject'/>

Create a ViewModel with a collection of Client objects:

<snippet id='autocomplete-clients-viewmodel'/>

**Example when `SuggestMode="Suggest"`**:

<snippet id='autocomplete-suggestmode-suggest'/>

Here is the result when `SuggestMode` is set to `Suggest`:

![AutoComplete Suggest](images/autocomplete-suggest-mode-suggest.png "AutoComplete Suggest")

**Exmaple when `SuggestMode="Append"`**:

<snippet id='autocomplete-suggestmode-append'/>

And the final result:

![AutoComplete Append](images/autocomplete-suggest-mode-append.png "AutoComplete Append")

**Example when `SuggestMode="SuggestAppend"`**:

<snippet id='autocomplete-suggestmode-suggest-append'/>

Here is the result:

![AutoComplete SuggestAppend](images/autocomplete-suggest-mode-suggestappend.png "AutoComplete SuggestAppend")

>important For AutoComplete Suggest Mode example refer the [SDKBrowser Demo application]({%slug sdkbrowser-app%}).

# See Also

- [Display Text]({%slug autocomplete-display-text-formatter%})
- [Tokens Support]({%slug autocomplete-tokens-support%})
- [Remote Search]({%slug autocomplete-remote-search%})
- [Filtering]({%slug autocomplete-filtering%})
- [Events]({%slug autocomplete-events%})
- [Methods]({%slug autocomplete-methods%})
- [Templates]({%slug autocomplete-custom-templates%})
- [Styling]({%slug autocomplete-styling%})