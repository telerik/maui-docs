---
title: Migrating from Xamarin
page_title: Migrating the Accordion from Xamarin.Forms to .NET MAUI
description: Learn how to migrate the Telerik UI for Xamarin Accordion to the Telerik UI for .NET MAUI framework by updating the namespaces and the incompatible NuGet packages
position: 20
slug: accordion-migrate-from-xamarin
---

# Migrating the Accordion from Xamarin to .NET MAUI

Telerik .NET MAUI Accordion control preserves the same API as Xamarin.Forms Accordion with a few changes and improvements. All changes are listed in the tables below:

## Migrating the Namespaces

| Control | Control name | XAML Namespcace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin Accordion | `RadAccordion` | xmlns:telerikPrimitives="clr-namespace:Telerik.XamarinForms.Primitives;assembly=Telerik.XamarinForms.Primitives" | using Telerik.XamarinForms.Primitives; |
| .NET MAUI Accordion | `RadAccordion` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |

## Modifying the API

| Xamarin Accordion | .NET MAUI Accordion |
| ------------- | --------------- |
| - | `CanExpandMultipleItems` |
| - | `Items` |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})
- [.NET MAUI Accordion Product Page](https://www.telerik.com/maui-ui/accordion)
- [.NET MAUI Forum Page](https://www.telerik.com/forums/maui?tagId=1853)
