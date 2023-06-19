---
title: Overview
page_title: .NET MAUI DataForm Documentation - Editors
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

## Common Properties for built-in editors

* `Placeholder`(`string`)&mdash;Specifies the placeholder value to display, when there is no input in the editor.
* `PropertyName`(`string`)&mdash;Specifies the name of the property from the business object this editor is bound to.
* `PropertyValue`(`object`)&mdash;Defines the value of the property from the business object this editor is bound to.
* `EditorValue`(`object`)&mdash;Specifies the current edited value, before applying it to the business object.
* `IsReadOnly`(`bool?`)&mdash;Specifies whether the current editor is in a read-only mode.
* `ValidationMode`(`Telerik.Maui.Controls.DataFormValidationMode`)&mdash;Inherits the ValidationMode from the DataForm.
* `CommitMode`(`Telerik.Maui.Controls.DataFormCommitMode`)&mdash;Inherits the CommitMode from the DataForm.
* `ColumnSpacing`(`double`)&mdash;Specifies the horizontal spacing between the rows in the editor.
* `RowSpacing`(`double`)&mdash;Specifies the vertical spacing between the rows in the editor.
* `ErrorDisplayOptions`(`Telerik.Maui.Controls.DataFormErrorDisplayOptions?`)&mdash;Specifies the display options of the header.
* `ErrorLength`(`Microsoft.Maui.GridLength`)&mdash;Specifies the length of the error in the editor. This property has an effect only when the `Telerik.Maui.Controls.DataFormEditor.ErrorPosition` property is set to `Beside`.
* `ErrorPosition`(`Telerik.Maui.Controls.DataFormErrorPosition?`)&mdash;Specifies the error position in the editor.
* `ErrorImageSource`(`Telerik.Maui.Controls.ImageSource`)&mdash;Specifies the image source of the error icon.

## Events

* `EditorGenerated`&mdash;Raised when the data form is about to generate an editor for a given property automatically. 
This event can be used to customize the automatic generation of the editors when the `Telerik.Maui.Controls.RadDataForm.AutoGenerateItems` property is set to `true` and there is no editor specified explicitly for the given property in the `Telerik.Maui.Controls.RadDataForm.Items` collection. 
It is possible to customize, replace or discard the generated editor, before it is added to the data form. The `EditorGenerated` event handler receives two parameters:
	* `sender` argument which is of type object, but can be cast to the `RadDataForm` type.
	* `DataFormEditorGeneratedEventArgs` which has a reference to the `PropertyName`(Gets the name of property from the data model, for which to generate an editor), `PropertyType`(Gets the type of property from the data model, for which to generate an editor) and `Editor`(Specifies the editor which is generated for the specified property. To skip the generation of the editor, set the property to `null`)

<snippet id='dataform-editorgenerated-event'/>

And the handler:

<snippet id='dataform-oneditors-generated'/>

> For CustomGenerate example refer to the DataForm/GettingStarted Category of the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}).

* `EditorValueChanged`&mdash;Raised when the value of an editor has changed. The `EditorValueChanged` event handler receives two parameters:
	* `sender` argument which is of type object, but can be cast to the `RadDataForm` type.
	* `DataFormEditorValueChangedEventArgs` which has a reference to the PropertyName, EditorValue and PropertyValue of the concrete editor.

## Custom Editors

You can define a custom editor using the `DataFormCustomEditor`. This editor inherits from DataFormEditor. More information on this can be found in [Custom Editors]({%slug dataform-custom-editor%}) article.

## See Also

- [Commit Data]({%slug dataform-commit-data%})
- [Validation]({%slug dataform-validation%})