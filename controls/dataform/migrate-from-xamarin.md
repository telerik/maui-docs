---
title: Migrate from Xamarin.Forms
page_title: .NET MAUI DataForm Documentation - Migrate from Xamarin
description: "Learn how to migrate from Xamarin.Forms DataForm to .NET MAUI DataForm control."
position: 2
slug: dataform-migrate-from-xamarin
---

# Migrate from Xamarin.Forms DataForm to .NET MAUI DataForm

Overall, Telerik .NET MAUI DataForm control is a complete new control with new API, improvements and flexible styling mechanisum implemented.

## Migrate the Namespaces

| Control | Control name | XAML Namespcace | C# Namespace|
| --------------- | --------------- | --------------- | --------------- |
| Xamarin DataForm | `RadDataForm` | xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.XamarinForms.Input" | using Telerik.XamarinForms.Input; | 
| .NET MAUI DataForm | `RadDataForm` | xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui" | using Telerik.Maui.Controls; |


## API Changes

Compared API changes in Xamarin.Forms DataForm and .NET MAUI DataForm are described in the table below:

| Xamarin DataForm | .NET MAUI DataForm |
| ------------- | --------------- |
| Source | gets the data directly from the set BindingContext |
| Telerik.XamarinForms.Common.DataAnnotations | System.ComponentModel.DataAnnotations.DataAnnotations |
| Validation modes - `Immediate`, `OnLostFocus`, `Manual` | Validation modes - `PropertyChanged`, `LostFocus`, `Explicit` |
| `FormValidationCompleted`, `PropertyValidationCompleted` | - |
| `ValidateAll`, `ValidateProperty` | - |
| - | `ValidateChanges` |
| - | `ValidateCommand`, `CancelCommand`, `CommitCommand` |
| Commit modes - `Immediate`, `OnLostFocus`, `Manual` | Commit modes - `PropertyChanged`, `LostFocus`, `Explicit` |
| `CommitAll`, `CommitProperty` | `CommitChanges` | - | 
| - | CancelChanges |
| DataFormGroupStackLayoutDefinition | DataFormVerticalStackLayout |
| `DataFormGroupGridLayoutDefinition`  | `DataFormGridLayout`  |
| -  | `DataFormCustomLayout`  |
| `DataFormGroupGridLayoutDefinition`  | `DataFormGridLayout` |
| -  | `DataFormCustomLayout` |

## Editors

Telerik Xamarin.Forms DataForm control uses native editors while in the .NET MAUI DataForm editors the main controls used are from Telerik .NET MAUI and .NET MAUI. 

Compared editors are displayed in the table below:

| Xamarin DataForm | .NET MAUI DataForm |
| ------------- | --------------- |
| `TextEditor` | `DataFormRadEntryEditor` |
| `SliderEditor` | - |
| - | `DataFormRadComboBoxEditor` |
| - | `DataFormRadEntryPasswordEditor` |
| - | `DataFormRadTextMaskedEditor` |
| - | `DataFormRadNumericMaskedEditor` |
| - | `DataFormRadEmailMaskedEditor` |
| - | `DataFormRadRegexMaskedEditor` |
| `IntegerEditor` | - |
| `DecimalEditor` | `DataFormRadNumericEditor` |
| `NumberPickerEditor` | - |
| `CheckBoxEditor` | `DataFormRadCheckBoxEditor` |
| `ToggleButtonEditor` | `DataFormSwitchEditor` |
| `SegmentedEditor` | `DataFormRadSegmentedEditor` |
| `DataFormGroupStackLayoutDefinition` | `DataFormVerticalStackLayout` |
| `DateEditor`  | `DataFormRadDatePickerEditor`, `DataFormDatePickerEditor` |
| `TimeEditor`  | `DataFormRadTimePickerEditor`, `DataFormTimePickerEditor`  |
| -  | `RadDateTimePickerEditor` |
| `CustomEditor`  | - |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI Application]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})