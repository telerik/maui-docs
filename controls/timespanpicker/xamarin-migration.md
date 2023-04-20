---
title: Migrating from Xamarin
page_title: Migrating the TimeSpanPicker from Xamarin.Forms to .NET MAUI
description: "Learn how to migrate the Telerik UI for Xamarin TimeSpanPicker to the Telerik UI for .NET MAUI framework by updating the namespaces and the incompatible NuGet packages. "
tags: maui, dotnet maui, telerik maui, migration, xamarin.forms
slug: migrate-xamarin-timespanpicker-to-maui
position: 20
---

# Migrating the TimeSpanPicker from Xamarin to .NET MAUI

The Telerik UI for .NET MAUI TimeSpanPicker preserves the same API as its Xamarin counterpart except for the configuration options listed in this article.

## Migrate Namespaces

| Control | Control name | XAML Namespcace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin TimeSpanPicker | `RadTimeSpanPicker` | xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.XamarinForms.Input" | using Telerik.XamarinForms.Input; |
| .NET MAUI TimeSpanPicker | `RadTimeSpanPicker` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"` | using Telerik.Maui.Controls; |


## API Changes

| Xamarin TimeSpanPicker | .NET MAUI TimeSpanPicker |
| ------------- | --------------- |
| `SelectorSettings` | `PopupSettings` |
| `PickerPopupSelectorSettings` | `PickerPopupSettings` |
| - | `PickerMode` |
| - | `DropDownSettings` |
| - | `PickerDropDownSettings` |
| - | `IsToggleButtonVisible` |
| - | `ToggleButtonStyle` |
| - | `IsClearButtonVisible` |
| - | `ClearButtonStyle` |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI Application]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})
