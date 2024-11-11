---
title: Migrating from Xamarin
page_title: Migrating the BadgeView from Xamarin.Forms to .NET MAUI
description: Learn how to migrate the Telerik UI for Xamarin BadgeView to the Telerik UI for .NET MAUI BadgeView by updating the namespaces, the incompatible NuGet packages and API.
tags: dot net maui, .net maui vs xamarin, maui vs xamarin, net maui vs xamarin, migration, xamarin.forms
position: 100
slug: badgeview-migrate-from-xamarin
---

# Migrating the BadgeView from Xamarin.Forms to .NET MAUI

Telerik .NET MAUI BadgeView control preserves the same API as its Xamarin counterpart except for the configuration options listed in this article.

The tables in the following sections list the differences between the APIs of the Xamarin.Forms BadgeView and .NET MAUI BadgeView.

## Namespaces Differences

When migrating the BadgeView from Xamarin to .NET MAUI, consider the following differences in the namespaces:

| Control | Control name | XAML Namespace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin BadgeView | `RadBadgeView` | xmlns:telerikPrimitives="clr-namespace:Telerik.XamarinForms.Primitives;assembly=Telerik.XamarinForms.Primitives" | using Telerik.XamarinForms.Primitives; |
| .NET MAUI BadgeView | `RadBadgeView` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls.Compatibility.Primitives; |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug sampleapps-overview %})
* [.NET MAUI BadgeView Product Page](https://www.telerik.com/maui-ui/badgeview)
* [.NET MAUI BadgeView Forum Page](https://www.telerik.com/forums/maui?tagId=1900)
