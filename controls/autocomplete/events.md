---
title: Events
page_title: .NET MAUI AutoComplete Documentation - Events
description: "Review the different events that are triggered on text changed, when return key is pressed, items are filtered and more."
position: 7
slug: autocomplete-events
---

# .NET MAUI AutoComplete Events

AutoComplete for .NET MAUI exposes the following events:

* `TextChanged`&mdash;Occurs when the text is changed. The TextChanged event handler receives a `TextChangedEventArgs` argument containing data related to this event. The `TextChangedEventArgs` provides the following properties:
	* `NewTextValue`(`string`)&mdash;which gets the new text value.
	* `OldTextValue`(`string`)&mdash;that gets the old text value.
	
>important You can find a working demo labeled **Remote Search** in the AutoComplete/Features folder of the [SDKBrowser Demo application]({%slug sdkbrowser-app%}).

* `SuggestionItemSelected`&mdash;Occurs when an item is selected from the SuggestionsView. The `SuggestionItemSelected` event handler receives two parameters:
	* The `sender` argument which is of type object, but can be cast to the `RadAutoComplete` type.
	* A `SuggestionItemSelectedEventArgs` object which has a reference to the selected item through its `DataItem` property.

* `FilteredItemsChanged`&mdash;Occurs when the FilteredItems collection is updated. The `FilteredItemsChanged` event handler receives two parameters:
	* The `sender` argument which is of type object, but can be cast to the `RadAutoComplete` type.
	* A `FilteredItemsChangedEventArgs` object which has a reference to filtered items collection its `FilteredItems` property.

* `Completed`&mdash;Occurs when the user finalizes the text in an entry with the return key.

# See Also

