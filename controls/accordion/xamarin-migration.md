---
title: Migrating from Xamarin
page_title: Migrating the Accordion from Xamarin.Forms to .NET MAUI
description: Learn how to migrate the Telerik UI for Xamarin Accordion to the Telerik UI for .NET MAUI Accordion by updating the namespaces, the incompatible NuGet packages and API.
tags: dot net maui, .net maui vs xamarin, maui vs xamarin, net maui vs xamarin, migration, xamarin.forms
position: 100
previous_url: /controls/accordion/migrate-from-xamarin
slug: accordion-xamarin-migration
---

# Migrating the Accordion from Xamarin.Forms to .NET MAUI

Telerik .NET MAUI Accordion control preserves the same API as its Xamarin counterpart except for the configuration options listed in this article.

## Namespaces Differences

When migrating the Accordion from Xamarin to .NET MAUI, consider the following differences in the namespaces:

| Control | Control name | XAML Namespace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin Accordion | `RadAccordion` | xmlns:telerikPrimitives="clr-namespace:Telerik.XamarinForms.Primitives;assembly=Telerik.XamarinForms.Primitives" | using Telerik.XamarinForms.Primitives; |
| .NET MAUI Accordion | `RadAccordion` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |

## API Differences

When migrating the Accordion from Xamarin to .NET MAUI, consider the following differences in the API:

| Xamarin Accordion | .NET MAUI Accordion |
| ------------- | --------------- |
| N/A | `CanExpandMultipleItems` |
| N/A | `Items` |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})
* [.NET MAUI Accordion Product Page](https://www.telerik.com/maui-ui/accordion)
* [.NET MAUI Forum Page](https://www.telerik.com/forums/maui?tagId=1853)
