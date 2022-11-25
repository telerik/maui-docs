---
title: Migrate from Xamarin.Forms
page_title: .NET MAUI MaskedEntry Documentation - Migrate from Xamarin
description: "Learn how to migrate from Xamarin.Forms MaskedInput to .NET MAUI MaskedEntry control."
position: 1
slug: maskedentry-migrate-from-xamarin
---

# Migrate from Xamarin.Forms MaskedInput to .NET MAUI MaskedEntry

Overall, Telerik .NET MAUI MaskedEntry control is a complete new control with new API, improvements and flexible styling mechanisum implemented.

Compared API changes in Xamarin.Forms MaskedInput and .NET MAUI MaskedEntry are described in the table below:

| Xamarin MaskedInput | .NET MAUI MaskedEntry |
| ------------- | --------------- |
| MaskType&mdash; Regex, Text | There isn't a MaskType property. Separate masks&mdash; Text Mask, Email Mask, Numeric Mask, Regex Mask, IP Mask |
| Mask| Mask |
| InvalidInputErrorText | ValidationErrorMessage |
| WatermarkText | Placeholder |
| InputValue | Value |
| - | ValueFormat |
| Placeholder | PromptChar |
| ApplyMaskedStarted | - |
| ApplyMaskedFinished | - |
| - | ValueChanging |
| - | ValueChanged |
| - | Localization Support |
| - | Globalization Support |
| - | Null Values Support |
