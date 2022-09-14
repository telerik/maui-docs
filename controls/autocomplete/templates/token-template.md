---
title: Token Template
page_title: .NET MAUI AutoComplete Documentation - Token Template
description: Check our &quot;Token Template&quot; documentation article for Telerik AutoComplete for .NET MAUI control.
position: 2
slug: autocomplete-token-template
---

# Token Customization

AutoComplete provides an option to customize the template that vizualize the tokens through `TokenTemplate` property.

* `TokenTemplate`(`DataTemplate`)&mdash;Defines the template used to vizualize the tokens.

## Example

Here is an example how to use the RadAutoComplete TokenTemplate:

**1.** Create the needed business objects, for example type City with the following properties:

<snippet id='autocomplete-city-businessobject'/>

**2.** Create a ViewModel with a collection of City objects:

<snippet id='autocomplete-city-viewmodel'/>

**3.** The following snippet shows the TokenTemplate definition:

<snippet id='autocomplete-templates-token-template-xaml'/>

and the code for Label.GestureRecognizer property:

<snippet id='autocompleteview-templates-token-template-labelgesture'/>

Here is the result:

![.NET MAUI AutoComplete TokenTemplate Example](images/autocomplete-token-template.png "AutoComplete TokenTemplate Example")

>important For AutoComplete Tokens Template example refer to the [SDKBrowser Demo application]({%slug sdkbrowser-app%}).

## See Also

