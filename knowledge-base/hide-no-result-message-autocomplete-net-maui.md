---
title: How to Hide the No Result Message in the AutoComplete for .NET MAUI
description: Learn how to hide the No Result message popup in the AutoComplete control for .NET MAUI
type: how-to
page_title: How to Hide the No Result Message in the AutoComplete for .NET MAUI
slug: hide-no-result-message-autocomplete-net-maui
tags: autocomplete, .net maui, hide, no result message
res_type: kb
---
# Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 6.7.0 | Telerik UI for .NET MAUI ComboBox | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

## Description

I want to hide the **No result** message window in the AutoComplete control for .NET MAUI when the entered email has not been saved in the system.

## Solution

To hide the **No results** message when there is nothing to show:

**1.** Set the `NoResultsMessage` property to an empty string.

```xml
<telerik:RadAutoComplete x:Name="autoComplete" NoResultsMessage=" " ... />
```
The message won't be displayed but the Suggestion View will be visible. If you want to hide the Suggestion View:

**2.** Set the `SuggestionViewBackgroundColor` property to a transparent color.

```xml
<telerik:RadAutoComplete x:Name="autoComplete" SuggestionViewBackgroundColor="Transparent" ... />
```

**3.** Set the `SuggestionViewBorderColor` property to a transparent color.

```xml
<telerik:RadAutoComplete x:Name="autoComplete" SuggestionViewBorderColor="Transparent" ... />
```

**4.** Set the `SuggestionViewBorderThickness` property to `0`.

```xml
<telerik:RadAutoComplete x:Name="autoComplete" SuggestionViewBorderThickness="0" ... />
```

**5.** Set the `SuggestionViewHeight` property to `0`.
```xml
<telerik:RadAutoComplete x:Name="autoComplete" SuggestionViewHeight="0" ... />
```

Note: Make sure to adjust the property values according to your specific implementation.

## See Also

- [AutoComplete for .NET MAUI Documentation](https://docs.telerik.com/devtools/maui/controls/autocomplete/overview)
