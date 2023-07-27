---
title: Migrating from Xamarin
page_title: Migrating the TemplatedPicker from Xamarin.Forms to .NET MAUI
description: Learn how to migrate the Telerik UI for Xamarin TemplatedPicker to the Telerik UI for .NET MAUI framework by updating the namespaces and the incompatible NuGet packages.
tags: maui, dotnet maui, telerik maui, migration, xamarin.forms
slug: migrate-xamarin-templatedpicker-to-maui
position: 20
---

# Migrating the TemplatedPicker from Xamarin to .NET MAUI

The Telerik UI for .NET MAUI TemplatedPicker preserves the same API as its Xamarin counterpart except for the configuration options listed in this article.

## Migrating the Namespaces

| Control | Control name | XAML Namespcace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin TemplatedPicker | `RadTemplatedPicker` | xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.XamarinForms.Input" | using Telerik.XamarinForms.Input; |
| .NET MAUI TemplatedPicker | `RadTemplatedPicker` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |


## Modifying the API

| Xamarin TemplatedPicker | .NET MAUI TemplatedPicker |
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
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})
- [.NET MAUI TemplatedPicker Product Page](https://www.telerik.com/maui-ui/templatedpicker)
- [.NET MAUI Forum Page](https://www.telerik.com/forums/maui?tagId=1853)
