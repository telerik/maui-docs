#highlighted-behavior
**Example: Removing the highlighted item**

```C#
var autoComplete = new RadAutoComplete();
autoComplete.HighlightItemFunc = (filteredItems, searchText) => null;
```

**Example: Setting the highlighted item to the last item from the SuggestionView**

```C#
var autoComplete = new RadAutoComplete();
autoComplete.HighlightItemFunc = (filteredItems, searchText) => filteredItems.LastOrDefault();
```
#end