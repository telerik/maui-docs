---
title: Migrating from Xamarin
page_title: Migrating the TimePicker from Xamarin.Forms to .NET MAUI
description: "Learn how to migrate the Telerik UI for Xamarin TimePicker to the Telerik UI for .NET MAUI framework by updating the namespaces and the incompatible NuGet packages. "
tags: maui, dotnet maui, telerik maui, migration, xamarin.forms
slug: migrate-xamarin-timepicker-to-maui
position: 2
---

# Migrating the TimePicker from Xamarin to .NET MAUI

The Telerik UI for .NET MAUI TimePicker preserves the same API as its Xamarin counterpart except for the configuration options listed in this article.

## Migrate Namespaces

| Control | Control name | XAML Namespcace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin TimePicker | `RadTimePicker` | `xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.XamarinForms.Input"` | `using Telerik.XamarinForms.Input;` | 
| .NET MAUI TimePicker | `RadTimePicker` | `xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"` | `using Telerik.Maui.Controls;` |


## API Changes

| Xamarin TimePicker | .NET MAUI TimePicker |
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
