---
title: Migrating from Xamarin
page_title: Migrating the AutoComplete from Xamarin.Forms to .NET MAUI
description: "Learn how to migrate the Telerik UI for Xamarin AutoComplete to the Telerik UI for .NET MAUI framework by updating the namespaces and the incompatible NuGet packages."
position: 20
slug: autocomplete-migrate-from-xamarin
---

# Migrating the AutoComplete from Xamarin to .NET MAUI

Telerik .NET MAUI AutoComplete control preserves the same API as Xamarin.Forms AutoCompleteView with a few changes and improvements. All changes are listed in the tables below:

## Migrating the Namespaces

| Control | Control name | XAML Namespcace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin AutoCompleteView | `RadAutoCompleteView` | xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.XamarinForms.Input" | using Telerik.XamarinForms.Input; |
| .NET MAUI AutoComplete | `RadAutoComplete` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |

## Modifying the API

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

* [Migrating from Xamarin.Forms to .NET MAUI]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})
- [.NET MAUI AutoComplete Product Page](https://www.telerik.com/maui-ui/autocomplete)
- [.NET MAUI Forum Page](https://www.telerik.com/forums/maui?tagId=1853)
