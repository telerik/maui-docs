---
title: Overview
page_title: .NET MAUI DataForm Documentation | Editors
description: "Check our &quot;Editors&quot; documentation article for Telerik DataForm for .NET MAUI control."
position: 0
slug: dataform-editors
---

# .NET MAUI DataForm Editors

The Telerik DataFrom control supports built-in editors.

The table below describes the available editors which use the Telerik .NET MAUI controls:

| Editor name 		 | Type | Input control |
|--------------------|------------|-------|
| `DataFormRadEntryEditor` 		 | `string` | `Telerik .NET MAUI RadEntry` |
| `DataFormRadEntryPasswordEditor` 		 | `string` | `Telerik .NET MAUI RadEntry` |
| `DataFormRadTextMaskedEditor` 		 | `string` | `Telerik .NET MAUI RadTextMaskedEntry` |
| `DataFormRadNumericMaskedEditor` 		| `object` | `Telerik .NET MAUI RadNumericMaskedEntry` |
| `DataFormRadEmailMaskedEditor` 		 | `string` | `Telerik .NET MAUI RadEmailMaskedEntry` |
| `DataFormRadRegexMaskedEditor` 		 | `string` | `Telerik .NET MAUI RadRegexMaskedEntry` |
| `DataFormRadNumericEditor` 		 | `double?` | `Telerik .NET MAUI RadNumericInput` |
| `DataFormRadDatePickerEditor`	 | `DateTime?` | `Telerik .NET MAUI RadDatePicker` |
| `DataFormRadDateTimePickerEditor`		| `DateTime?` | `Telerik .NET MAUI RadDateTimePicker` |
| `DataFormRadTimePickerEditor`		| `TimeSpan?` | `Telerik .NET MAUI RadTimePicker` |
| `DataFormRadTimeSpanPickerEditor` 	 | `TimeSpan?` | `Telerik .NET MAUI RadTimeSpanPicker` |
| `DataFormRadListPickerEditor`     | `enum` | `Telerik .NET MAUI RadListPicker` |
| `DataFormRadComboBoxEditor`		 | `enum` | `Telerik .NET MAUI RadComboBox` |
| `DataFormRadCheckBoxEditor`		 | `bool?` | `Telerik .NET MAUI RadCheckBox` |
| `DataFormRadSegmentedEditor`		 | `enum` | `Telerik .NET MAUI RadSegmentedControl` |

The table below describes the available editors which use the .NET MAUI controls:

| Editor name 		 | Type | Input control |
|--------------------|------------|-------|
| `DataFormMultiLineEditor` 		 | `string` | `.NET MAUI Editor` |
| `DataFormDatePickerEditor`	 | `DateTime?` | ` .NET MAUI DatePicker` |
| `DataFormTimePickerEditor`		| `TimeSpan?` | ` .NET MAUI TimePicker` |
| `DataFormSwitchEditor`		 | `bool` | `.NET MAUI Switch` |

## Common Properties

* `Placeholder`(`string`)&mdash;Specifies the placeholder value to display, when there is no input in the editor.
* `PropertyName`(`string`)&mdash;Specifies the name of the property from the business object this editor is bound to.
* `PropertyValue`(`object`)&mdash;Defines the value of the property from the business object this editor is bound to.
* `EditorValue`(`object`)&mdash;Specifies the current edited value, before applying it to the business object.
* `IsReadOnly`(`bool?`)&mdash;Specifies whether the current editor is in a read-only mode.
* `ValidationMode`(`Telerik.Maui.Controls.DataFormValidationMode`)&mdash;Defines the current validation mode of the DataForm editor.
* `CommitMode`(`Telerik.Maui.Controls.DataFormCommitMode`)&mdash;Specifies the current commit mode of the DataForm editor.
* `ColumnSpacing`(`double`)&mdash;Specifies the horizontal spacing between the rows in the editor.
* `RowSpacing`(`double`)&mdash;Specifies the vertical spacing between the rows in the editor.

* Properties related to the header position, text and style are described in the [Header article]({%slug dataform-headers%}).

* `ErrorDisplayOptions`(`Telerik.Maui.Controls.DataFormErrorDisplayOptions?`)&mdash;Specifies the display options of the header.
* `ErrorLength`(`Microsoft.Maui.GridLength`)&mdash;Specifies the length of the error in the editor. This property has an effect only when the `Telerik.Maui.Controls.DataFormEditor.ErrorPosition` property is set to `Beside`.
* `ErrorPosition`(`Telerik.Maui.Controls.DataFormErrorPosition?`)&mdash;Specifies the error position in the editor.
* `ErrorImageSource`(`Telerik.Maui.Controls.ImageSource`)&mdash;Specifies the image source of the error icon.

* Properties related to the error styling are described in the [Error message styling article]({%slug dataform-error-message-styling}).

## Styling

For more information about how to style the editors, review the [Editors Styling article]({%slug dataform-editors-styling%}).