---
title: Migrating from Xamarin
page_title: Migrating the DatePicker from Xamarin.Forms to .NET MAUI
description: "Learn how to migrate the Telerik UI for Xamarin DatePicker to the Telerik UI for .NET MAUI framework by updating the namespaces and the incompatible NuGet packages. "
tags: maui, dotnet maui, telerik maui, migration, xamarin.forms
slug: migrate-xamarin-datepicker-to-maui
position: 2
---

# Migrating the DatePicker from Xamarin to .NET MAUI

The Telerik UI for .NET MAUI DatePicker preserves the same API as its Xamarin counterpart except for the configuration options listed in this article.

## Migrate Namespaces

| Control | Control name | XAML Namespcace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin DatePicker | `RadDatePicker` | `xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.XamarinForms.Input"` | `using Telerik.XamarinForms.Input;` | 
| .NET MAUI DatePicker | `RadDatePicker` | `xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"` | `using Telerik.Maui.Controls;` |


## API Changes

| Xamarin DatePicker | .NET MAUI DatePicker |
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
