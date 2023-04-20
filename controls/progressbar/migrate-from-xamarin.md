---
title: Migrating from Xamarin
page_title: Migrating the ProgressBar from Xamarin.Forms to .NET MAUI
description: "Learn how to migrate the Telerik UI for Xamarin ProgressBar to the Telerik UI for .NET MAUI framework by updating the namespaces and the incompatible NuGet packages."
position: 20
slug: progressbar-migrate-from-xamarin
---

# Migrate from Xamarin.Forms ProgressBar to .NET MAUI ProgressBar

Overall, Telerik .NET MAUI ProgressBar control preserves the same API as Xamarin.Forms ProgressBar with a few changes and improvements listed in the table below:

## Migrating the Namespaces

| Control | Control name | XAML Namespcace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin ProgressBar | `RadProgressBar` | xmlns:telerikPrimitives="clr-namespace:Telerik.XamarinForms.Primitives;assembly=Telerik.XamarinForms.Primitives" | using Telerik.XamarinForms.Primitives; |
| .NET MAUI ProgressBar | `RadProgressBar` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"` | using Telerik.Maui.Controls; |

## Modifying the API

| Xamarin ProgressBar | .NET MAUI ProgressBar |
| ------------- | --------------- |
| `IndeterminateFill` | `ProgressFill` |
| - | `ProgressCornerRadius` |
| - | `TrackCornerRadius` |
| - | `TrackThickness` |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})
- [.NET MAUI ProgressBar Product Page](https://www.telerik.com/maui-ui/progressbar)
- [.NET MAUI Forum Page](https://www.telerik.com/forums/maui?tagId=1853)
