---
title: Migrate from Xamarin.Forms
page_title: .NET MAUI MaskedEntry Documentation - Migrate from Xamarin
description: "Learn how to migrate from Xamarin.Forms MaskedInput to .NET MAUI MaskedEntry control."
position: 1
slug: maskedentry-migrate-from-xamarin
---

# Migrate from Xamarin.Forms MaskedInput to .NET MAUI MaskedEntry

Overall, Telerik .NET MAUI MaskedEntry control is a complete new control with new API, improvements and flexible styling mechanisum implemented.

## Migrate Namespaces

| Control | Control name | XAML Namespcace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin MaskedInput | `RadMaskedInput` | xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.XamarinForms.Input" | using Telerik.XamarinForms.Input; | 
| .NET MAUI MaskedEntry | `RadMaskedEntry` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |

## API Changes

Compared API changes in Xamarin.Forms MaskedInput and .NET MAUI MaskedEntry are described in the table below:

| Xamarin MaskedInput | .NET MAUI MaskedEntry |
| ------------- | --------------- |
| MaskType&mdash;Regex, Text | There isn't a MaskType property. Separate masks&mdash;Text Mask, Email Mask, Numeric Mask, Regex Mask, IP Mask |
| `Mask` | `Mask` |
| `InvalidInputErrorText` | `ValidationErrorMessage` |
| `WatermarkText` | `Placeholder` |
| `InputValue` | `Value` |
| - | `ValueFormat` |
| `Placeholder` | `PromptChar` |
| `ApplyMaskedStarted` | - |
| `ApplyMaskedFinished` | - |
| - | `ValueChanging` |
| - | `ValueChanged` |
| - | Localization Support |
| - | Globalization Support |
| - | Null Values Support |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI Application]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})

