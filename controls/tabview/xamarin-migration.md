---
title: Migrating from Xamarin
page_title: Migrating the TabView from Xamarin.Forms to .NET MAUI
description: Learn how to migrate the Telerik UI for Xamarin TabView to the Telerik UI for .NET MAUI framework by updating the namespacesby updating the namespaces, the incompatible NuGet packages and API.
tags: maui, dotnet maui, telerik maui, migration, xamarin.forms, tabview
position: 100
slug: migrate-xamarin-tabview-to-maui
---

# Migrating the TabView from Xamarin.Forms to .NET MAUI

The Telerik UI for .NET MAUI TabView control has been designed and built from the ground up as a new control with a new API and significant improvements over its Xamarin counterpart.

The tables in the following sections list the differences between the APIs of the Xamarin.Forms TabView and .NET MAUI TabView.

## Namespaces Differences

When migrating the TabView from Xamarin to .NET MAUI, consider the following differences in the namespaces:

| Control | Control name | XAML Namespcace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin TabView | `RadTabView` | xmlns:telerikPrimitives="clr-namespace:Telerik.XamarinForms.Primitives;assembly=Telerik.XamarinForms.Primitives" | using Telerik.XamarinForms.Primitives; |
| .NET MAUI TabView | `RadTabView` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"` | using Telerik.Maui.Controls; |

## API Differences

When migrating the TabView from Xamarin to .NET MAUI, consider the following differences in the API:

| Xamarin TabView | .NET MAUI TabView |
| ------------- | --------------- |
| N/A | `ItemsSource` |
| N/A | `ItemTemplate` |
| `Items` | `Items` |
| `HeaderPosition` | `HeaderPosition` |
| `SelectedItem` | `SelectedItem` |
| N/A | `SelectedIndex` |
| `IsScrollable` | `IsHeaderScrollable` |
| N/A | `IsHeaderOverlaid` |
| Overflow button | N/A |
| `IsContentSwipingEnabled` | `IsContentSwipingEnabled` |
| `TabViewItem` | `TabViewItem` |
| N/A | `HeaderStyle` |
| N/A | `HeaderItemStyle` |
| N/A | `HeaderItemStyleSelector` |
| N/A | `ContentStyle` |

In Xamarin, the `TabViewHeaderItem` is part of the `TabViewItem`, while in .NET MAUI, the `TabViewHeader` is part of the `RadTabView`. Here is the API for the `TabViewItem`:

| Xamarin TabView | .NET MAUI TabView |
| ------------- | --------------- |
| `HeaderText` | `HeaderText` |
| `Header` | The header is part of the `RadTabView` |
| N/A | `ImageSource` |
| `Content` | `Content` |
| N/A | `ContentTemplate` |
| `IsSelected` | `IsSelected` |
| `IsEnabled` | `IsEnabled` |
| `IsVisible` | `IsVisible` |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug sampleapps-overview %})
- [.NET MAUI TabView Product Page](https://www.telerik.com/maui-ui/tabview)
- [.NET MAUI Forum Page](https://www.telerik.com/forums/maui?tagId=1871)
