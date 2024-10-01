---
title: Migrating from Xamarin
page_title: Migrating the SignaturePad from Xamarin.Forms to .NET MAUI
description: Learn how to migrate the Telerik UI for Xamarin SignaturePad to the Telerik UI for .NET MAUI framework by updating the namespaces and the incompatible NuGet packages.
position: 20
slug: signaturepad-migrate-from-xamarin
---

# Migrate from Xamarin.Forms SignaturePad to .NET MAUI SignaturePad

Telerik .NET MAUI SignaturePad control preserves the same API as Xamarin.Forms SignaturePad with a few changes and improvements listed in the table below:

## Migrating the Namespaces

| Control | Control name | XAML Namespcace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin SignaturePad | `RadSignaturePad` | xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.XamarinForms.Input" | using Telerik.XamarinForms.Input; |
| .NET MAUI SignaturePad | `RadSignaturePad` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |

## Modifying the API

| Xamarin SignaturePad | .NET MAUI SignaturePad |
| ------------- | --------------- |
| - | `Style` |
| - | `ActualStyle` |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug sampleapps-overview %})
- [.NET MAUI SignaturePad Product Page](https://www.telerik.com/maui-ui/signaturepad)
- [.NET MAUI Forum Page](https://www.telerik.com/forums/maui?tagId=1853)
