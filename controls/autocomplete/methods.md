---
title: Methods
page_title: .NET MAUI AutoComplete Documentation - Methods
description: Check our &quot;Methods&quot; documentation article for Telerik .NET MAUI AutoComplete control.
position: 9
slug: autocomplete-methods
---

# .NET MAUI AutoComplete Methods

AutoComplete for .NET MAUI exposes the ability to explicitly show/hide the popup containing all items through the following methods:

* `ShowSuggesstions`&mdash;Shows all items when the control receives focus.
* `HideSuggestions`&mdash;Hide all items when the control looses focus.

## Example

The example below uses `ShowSuggesstions` method to display all items as soon as the AutoComplete receives the focus. 

**1.** Create the needed business objects, for example type Client with the following properties:

<snippet id='autocomplete-client-businessobject'/>

**2.** Define a ViewModel with a collection of Client objects:

<snippet id='autocomplete-clients-viewmodel'/>

**3.** Declare the RadAutoComplete in XAML:

<snippet id='autocomplete-data-binding'/>

**4.** Use the following code to attach the focused event to the control:

<snippet id='autocomplete-focused'/>

**5.** Call the `ShowSuggestions` method inside the Focused event:

<snippet id='autocomplete-showsuggestions'/>

Here is the result:

![.NET MAUI AutoComplete Show Suggestions](images/autocomplete-showsuggestions.png "AutoComplete ShowSuggestions")

# See Also

- [Data Binding]({%slug autocomplete-data-binding%})
- [Configuration]({%slug autocomplete-configuration%})
- [Suggest Mode]({%slug autocomplete-suggest-mode%})
- [Display Text]({%slug autocomplete-display-text-formatter%})
- [Tokens Support]({%slug autocomplete-tokens-support%})
- [Remote Search]({%slug autocomplete-remote-search%})
- [Filtering]({%slug autocomplete-filtering%})
- [Events]({%slug autocomplete-events%})
- [Templates]({%slug autocomplete-custom-templates%})
- [Styling]({%slug autocomplete-styling%})
