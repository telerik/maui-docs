---
title: Migrating from Xamarin
page_title: Migrating the AutoComplete from Xamarin.Forms to .NET MAUI
description: Learn how to migrate the Telerik UI for Xamarin AutoCompleteView to the Telerik UI for .NET MAUI AutoComplete by updating the namespaces and the incompatible NuGet packages.
tags: dot net maui, .net maui vs xamarin, maui vs xamarin, net maui vs xamarin, migration, xamarin.forms
position: 20
previous_url: /controls/autocomplete/migrate-from-xamarin
slug: autocomplete-migrate-from-xamarin
---

# Migrating the AutoComplete from Xamarin to .NET MAUI

The Telerik UI for .NET MAUI AutoComplete preserves the same API as its Xamarin counterpart except for the configuration options listed in this article.

The tables in the following sections list any differences between the APIs of the Xamarin.Forms AutoCompleteView and .NET MAUI AutoComplete.

## Namespace Differences

When migrating the AutoCompleteView from Xamarin to .NET MAUI, consider the following differences in the namespaces:

| Control | Control name | XAML Namespcace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin AutoCompleteView | `RadAutoCompleteView` | xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.XamarinForms.Input" | using Telerik.XamarinForms.Input; |
| .NET MAUI AutoComplete | `RadAutoComplete` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |

## API Differences

When migrating the AutoComplete from Xamarin to .NET MAUI, consider the following differences in the API:

| Xamarin AutoCompleteView | .NET MAUI AutoComplete |
| ------------- | --------------- |
| `WatermarkText` | `Placeholder` |
| `WatermarkTextColor` | `PlaceholderColor` |
| `SuggestionItemTextColor` | `SuggestionItemHighlightTextColor` |
| `SuggestionItemTemplate` (`DataTemplate`) with `ViewCell` inside the Template | `SuggestionItemTemplate` (`DataTemplate`) |
| `SuggestionItemLabel` | `RadHighlightLabel` |
| `ImagePath` | N/A |
| `CompletionMode` (of type `CompletionMode`) | `CompletionMode` (of type `AutoCompleteCompletionMode`) |
| `SuggestionViewPosition` (of type `PopupPosition`) | `SuggestionViewPosition` (of type `AutoCompletePopupPosition`) |
| `SuggestMode` of type(`SuggestMode`) | `SuggestMode` (of type `AutoCompleteSuggestMode`) |
| `FilteredItemsChangedEventArgs` in namespace `Telerik.XamarinForms.Input.AutoComplete` | `FilteredItemsChangedEventArgs` in namespace `Telerik.Maui.Controls.AutoComplete` |
| `SuggestionItemSelectedEventArgs` in namespace `Telerik.XamarinForms.Input.AutoComplete` | `SuggestionItemSelectedEventArgs` in namespace `Telerik.Maui.Controls.AutoComplete` |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug sampleapps-overview %})
- [.NET MAUI AutoComplete Product Page](https://www.telerik.com/maui-ui/autocomplete)
- [.NET MAUI Forum Page](https://www.telerik.com/forums/maui?tagId=1853)
