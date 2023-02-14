---
title: Migrate from Xamarin.Forms
page_title: .NET MAUI AutoComplete Documentation - Migrate from Xamarin
description: "Learn how to migrate from Xamarin.Forms AutoCompleteView to .NET MAUI AutoCompolete control."
position: 1
slug: autocomplete-migrate-from-xamarin
---

# Migrate from Xamarin.Forms AutoCompleteView to .NET MAUI AutoComplete

Telerik .NET MAUI AutoComplete control preserves the same API as Xamarin.Forms AutoCompleteView with a few changes and improvements. All changes are listed in the tables below:

## Migrate the Namespaces

| Control | Control name | XAML Namespcace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin AutoCompleteView | `RadAutoCompleteView` | xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.XamarinForms.Input" | using Telerik.XamarinForms.Input; | 
| .NET MAUI AutoComplete | `RadAutoComplete` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |

## API Changes

| Xamarin AutoCompleteView | .NET MAUI AutoComplete |
| ------------- | --------------- |
| `WatermarkText` | `Placeholder` |
| `WatermarkTextColor` | `PlaceholderColor` |
| `SuggestionItemTextColor` | `SuggestionItemHighlightTextColor` |
| `SuggestionItemLabel` | `RadHighlightLabel` |
| `ImagePath` | - |
| `CompletionMode` (of type `CompletionMode`) | `CompletionMode` (of type `AutoCompleteCompletionMode`) |
| `SuggestionViewPosition` (of type `PopupPosition`) | `SuggestionViewPosition` (of type `AutoCompletePopupPosition`) |
| `SuggestMode` of type(`SuggestMode`) | `SuggestMode` (of type `AutoCompleteSuggestMode`) |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI Application]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})
