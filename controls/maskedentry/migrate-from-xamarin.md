---
title: Migrating from Xamarin
page_title: Migrating the MaskedInput from Xamarin.Forms to .NET MAUI
description: Learn how to migrate the Telerik UI for Xamarin MaskedInput to the Telerik UI for .NET MAUI framework by updating the namespaces and the incompatible NuGet packages.
position: 20
slug: maskedentry-migrate-from-xamarin
---

# Migrating the MaskedInput from Xamarin to .NET MAUI

The Telerik .NET MAUI MaskedEntry control is a completely new control, with a new API, various improvements, and a flexible styling mechanism.

## Migrating the Namespaces

| Control | Control name | XAML Namespcace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin MaskedInput | `RadMaskedInput` | xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.XamarinForms.Input" | using Telerik.XamarinForms.Input; |
| .NET MAUI MaskedEntry | `RadMaskedEntry` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |

## Modifying the API

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

* [Migrating from Xamarin.Forms to .NET MAUI]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})
- [.NET MAUI MaskedEntry Product Page](https://www.telerik.com/maui-ui/maskedentry)
- [.NET MAUI Forum Page](https://www.telerik.com/forums/maui?tagId=1853)
