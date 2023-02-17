---
title: Migrate from Xamarin.Forms
page_title: .NET MAUI SignaturePad Documentation - Migrate from Xamarin
description: "Learn how to migrate from Xamarin.Forms SignaturePad to .NET MAUI SignaturePad control."
position: 1
slug: signaturepad-migrate-from-xamarin
---

# Migrate from Xamarin.Forms SignaturePad to .NET MAUI SignaturePad

Overall, Telerik .NET MAUI SignaturePad control preserves the same API as Xamarin.Forms SignaturePad with a few changes and improvements listed in the table below:

## Migrate Namespaces

| Control | Control name | XAML Namespcace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin SignaturePad | `RadSignaturePad` | xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.XamarinForms.Input" | using Telerik.XamarinForms.Input; | 
| .NET MAUI SignaturePad | `RadSignaturePad` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |

## API Changes

| Xamarin SignaturePad | .NET MAUI SignaturePad |
| ------------- | --------------- |
| - | `Style` |
| - | `ActualStyle` |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI Application]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})

