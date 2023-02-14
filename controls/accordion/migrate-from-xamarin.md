---
title: Migrate from Xamarin.Forms
page_title: .NET MAUI Accordion Documentation - Migrate from Xamarin
description: "Learn how to migrate from Xamarin.Forms Accordion to .NET MAUI Accordion control."
position: 1
slug: accordion-migrate-from-xamarin
---

# Migrate from Xamarin.Forms Accordion to .NET MAUI SignaturePad

Telerik .NET MAUI Accordion control preserves the same API as Xamarin.Forms Accordion with a few changes and improvements. All changes are listed in the tables below:

## Migrate the Namespaces

| Control | Control name | XAML Namespcace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin Accordion | `RadAccordion` | xmlns:telerikPrimitives="clr-namespace:Telerik.XamarinForms.Primitives;assembly=Telerik.XamarinForms.Primitives" | using Telerik.XamarinForms.Primitives; | 
| .NET MAUI Accordion | `RadAccordion` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |

## API Changes

| Xamarin Accordion | .NET MAUI Accordion |
| ------------- | --------------- |
| - | `CanExpandMultipleItems` |
| - | `Items` |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI Application]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})

