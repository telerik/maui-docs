---
title: Migrate from Xamarin
page_title: .NET MAUI Conversational UI Documentation - Migrate from Xamarin
description: Learn how to migrate the Telerik UI for Xamarin RadChat to the Telerik UI for .NET MAUI framework by updating the namespaces and the incompatible NuGet packages
position: 3
slug: chat-migrate-from-xamarin
---

# Migrating the Chat from Xamarin to .NET MAUI

The Telerik UI for .NET MAUI Chat preserves the same API as its Xamarin counterpart except for the configuration options listed in this article.

## Migrate Namespaces

| Control | Control name | XAML Namespcace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin DatePicker | `RadChat` | xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.XamarinForms.Input" | using Telerik.XamarinForms.Input; | 
| .NET MAUI DatePicker | `RadChat` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |


## API Changes

| Xamarin RadChat | .NET MAUI RadChat |
| ------------- | --------------- |
| `NA` | `SuggestedActions` |
| `DisplayDate` | `SelectedDate` |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI Application]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})