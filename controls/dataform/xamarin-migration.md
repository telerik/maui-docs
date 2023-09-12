---
title: Migrating from Xamarin
page_title: .NET MAUI DataForm Documentation - Migrate from Xamarin
description: Learn how to migrate from Xamarin.Forms DataForm to the .NET MAUI DataForm control.
position: 100
tags: dot net maui, .net maui vs xamarin, maui vs xamarin, net maui vs xamarin, migration, xamarin.forms
previous_url: /controls/dataform/migrate-from-xamarin
slug: dataform-migrate-from-xamarin
---

# Migrate from Xamarin.Forms DataForm to .NET MAUI DataForm

The Telerik UI for .NET MAUI DataForm control has been designed and built from the ground up as a completely new control with a new API and significant improvements over its Xamarin counterpart.

The tables in the following sections list the differences between the APIs of the Xamarin.Forms DataForm and .NET MAUI DataForm.

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
| `RegisterEditor` | `EditorGenerated` |
| `EditorValueChanged` | `EditorValueChanged` |
| N/A | `GroupGenerated` |
| N/A |`HasPendingChanges` |
| N/A | `HasValidationErrors` |
| Validation modes - `Immediate`, `OnLostFocus`, `Manual` | Validation modes - `PropertyChanged`(immediate), `LostFocus`, `Explicit`(manual) |
| `ValidateAll` | `ValidateChanges` |
| `ValidateProperty` | `ValidateChanges(string propertyName)` |
| `FormValidationCompleted` | `ValidationCompleted` |
| `PropertyValidationCompleted` | `EditorValidationCompleted` |
| Commit modes - `Immediate`, `OnLostFocus`, `Manual` | Commit modes - `PropertyChanged`(immediate), `LostFocus`, `Explicit`(manual) |
| `CommitAll` | `CommitChanges` |
| `CommitProperty` | `CommitChanges(string propertyName)` |
| N/A | `CancelChanges` |
| N/A | `CancelChanges(string propertyName)` |
| N/A | `ValidateCommand` |
| N/A | `CancelCommand` |
| N/A | `CommitCommand` |
| `DataFormGroupStackLayoutDefinition` | `DataFormVerticalStackLayout` |
| `DataFormGroupGridLayoutDefinition`  | `DataFormGridLayout`  |
| N/A | `DataFormCustomLayout`  |

## Editors

Telerik Xamarin.Forms DataForm control uses native editors while in the .NET MAUI DataForm editors the main controls used are from Telerik .NET MAUI and .NET MAUI.

Compared editors are displayed in the table below:

| Xamarin DataForm | .NET MAUI DataForm |
| ------------- | --------------- |
| `TextEditor` | `DataFormRadEntryEditor` |
| `SliderEditor` | N/A |
| N/A | `DataFormRadComboBoxEditor` |
| N/A | `DataFormRadEntryPasswordEditor` |
| N/A | `DataFormRadTextMaskedEditor` |
| N/A | `DataFormRadNumericMaskedEditor` |
| N/A | `DataFormRadEmailMaskedEditor` |
| N/A | `DataFormRadRegexMaskedEditor` |
| `IntegerEditor` | N/A |
| `DecimalEditor` | `DataFormRadNumericEditor` |
| `NumberPickerEditor` | N/A |
| `CheckBoxEditor` | `DataFormRadCheckBoxEditor` |
| `ToggleButtonEditor` | `DataFormSwitchEditor` |
| `SegmentedEditor` | `DataFormRadSegmentedEditor` |
| `DataFormGroupStackLayoutDefinition` | `DataFormVerticalStackLayout` |
| `DateEditor`  | `DataFormRadDatePickerEditor`, `DataFormDatePickerEditor` |
| `TimeEditor`  | `DataFormRadTimePickerEditor`, `DataFormTimePickerEditor`  |
| N/A | `RadDateTimePickerEditor` |
| `CustomEditor` | `CustomEditor` |

## See Also

* [Migrating from Xamarin.Forms to .NET MAUI Application]({% slug migrate-to-net-maui %})
* [.NET MAUI Sample Applications]({% slug controls-samples-app %})
* [.NET MAUI DataForm Product Page](https://www.telerik.com/maui-ui/dataform)
* [.NET MAUI DataForm Forum Page](https://www.telerik.com/forums/maui?tagId=1979)
