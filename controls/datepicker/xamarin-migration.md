---
title: Migrating from Xamarin
page_title: Migrating the DatePicker from Xamarin.Forms to .NET MAUI
description: Learn how to migrate the Telerik UI for Xamarin DatePicker to the Telerik UI for .NET MAUI framework by updating the namespaces and the incompatible NuGet packages.
tags: maui, dotnet maui, telerik maui, migration, xamarin.forms
slug: migrate-xamarin-datepicker-to-maui
position: 30
---

# Migrating the DatePicker from Xamarin to .NET MAUI

The Telerik UI for .NET MAUI DatePicker preserves the same API as its Xamarin counterpart except for the configuration options listed in this article.

## Migrating the Namespaces

The following table lists the namespaces you need to update when migrating the DatePicker from Xamarin to .NET MAUI.

| Control | Control Name | XAML Namespcace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin DatePicker | RadDatePicker | xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.XamarinForms.Input" | using Telerik.XamarinForms.Input; |
| .NET MAUI DatePicker | RadDatePicker | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |


## Modifying the API

The following table lists the API reference calls you need to update when migrating the DatePicker from Xamarin to .NET MAUI.

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

* [Migrating from Xamarin.Forms to .NET MAUI]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug sampleapps-overview %})
- [.NET MAUI DatePicker Product Page](https://www.telerik.com/maui-ui/datepicker)
- [.NET MAUI Forum Page](https://www.telerik.com/forums/maui?tagId=1853)
