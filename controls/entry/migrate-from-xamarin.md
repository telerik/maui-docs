---
title: Migrate from Xamarin.Forms
page_title: .NET MAUI Entry Documentation - Migrate from Xamarin
description: "Learn how to migrate from Xamarin.Forms Entry to .NET MAUI Entry control."
position: 2
slug: entry-migrate-from-xamarin
---

# Migrate from Xamarin.Forms Entry to .NET MAUI Entry

Overall, Telerik .NET MAUI Entry control preserves the same API as Xamarin.Forms Entry with a few changes and improvements listed below.

| Xamarin Entry | .NET MAUI Entry |
| ------------- | --------------- |
| WatermarkText | Placeholder |
| WatermarkTextColor| PlaceholderColor |
| - | CharacterSpacing |
| - | IsTextPredictionEnabled |
| - | ReturnType |
| - | ClearButtonVisibility |
| CompletedCommand | ReturnCommand |
| BorderStyle.BorderColor | BorderBrush |
| BorderStyle.BorderThickness | BorderThickness |
| BorderStyle.CornerRadius | CornerRadius |
| - | ClearButtonColor |

## See Also

- [Text Appearance]({% slug entry-text-appearance%})
- [Events]({% slug entry-events%})
- [Commands]({%slug entry-commands%})
- [Styling]({% slug entry-styling%})
