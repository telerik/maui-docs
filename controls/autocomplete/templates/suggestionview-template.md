---
title: SuggestionView Template
page_title: .NET MAUI AutoCompleteView Documentation | SuggestionView Template
description: Check our &quot;SuggestionView Template&quot; documentation article for Telerik AutoComplete for .NET MAUI control.
position: 4
slug: autocomplete-suggestion-view-template
---

# Suggestion View Customization

AutoComplete provides the option to change the default template that visualize the filtered items and implement a custom template using `SuggestionViewTemplate` property.

* `SuggestionViewTemplate`(`DataTemplate`)&mdash;Defines the template used to visualize the filtered items

## Example

Here is an example how to use the RadAutoComplete SuggestionViewTemplate:

**1.** Create the needed business objects, for example type City with the following properties:

<snippet id='autocomplete-person-businessobject'/>

**2.** Create a ViewModel with a collection of City objects:

<snippet id='autocomplete-people-viewmodel'/>

**3.** The following snippet shows the SuggestionViewTemplate with RadDataGrid inside it:

<snippet id='autocomplete-templates-suggestion-view-template-xaml'/>

Here is the result:

![AutoComplete SuggestionViewTemplate Example](images/autocomplete-suggestionview-template.png "AutoComplete SuggestionItemTemplate Example")

>important For autoComplete SuggestionView Template example refer to the [SDKBrowser Demo application]({%slug sdkbrowser-app%}).

## See Also

