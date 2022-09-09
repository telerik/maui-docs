---
title: Data Binding
page_title: .NET MAUI AutoComplete Documentation - Data Binding
description: "Review the data binding oprions for .NET MAUI AutoComplete control."
position: 5
slug: autocomplete-data-binding
---

# .NET MAUI AutoComplete Data Binding

For all cases where the business items are not simple strings data-binding is necessary in order to correctly visualize information. The AutoComplete for .NET MAUI component supports data binding in the form of path properties.

* `TextSearchPath(`string`)&mdash;Defines the name of the property the search function will be executed against.

>The `TextSearchPath` property is required in data-binding scenarios.

The AutoComplete component provides a default template for suggestion items that cannot be modified. You can use a [custom template]({%slug autocomplete-suggestion-item-template%}) if you need to customize the suggestion items.

## Example

Here is an example how the RadAutoCompleteView Data Binding works:

**1.** Create the needed business objects, for example type Client with the following properties:

<snippet id='autocomplete-client-businessobject'/>

**2.** Ceate a ViewModel with a collection of Client objects:

<snippet id='autocomplete-clients-viewmodel'/>

**3.** Use the following snippet to declare a RadAutoComplete in XAML:

<snippet id='autocomplete-data-binding'/>

>important For AutoComplete Data Binding example refer to the [SDKBrowser Demo application]({%slug sdkbrowser-app%}).

# See Also
