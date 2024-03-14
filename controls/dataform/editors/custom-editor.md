---
title: Custom Editors
page_title: .NET MAUI DataForm Documentation - Custom Editors
description: Learn more about the custom editors that the Telerik UI for .NET MAUI DataForm control provides.
position: 5
slug: dataform-custom-editor
---

# .NET MAUI DataForm Custom Editors

DataForm has a support for custom editors with 5.1.0 version of Telerik UI for .NET MAUI.

* `DataFormCustomEditor`&mdash;Represents a custom editor in the `RadDataForm`.

## Properties

* `EditorTemplate`(`ControlTemplate`)&mdash;Defines the content of the custom editor. The target type of this template is `Telerik.Maui.Controls.DataFormCustomEditorContentPresenter`. The `DataFormCustomEditorContentPresenter` exposes the following properties:

	* `Value`(`object`)&mdash;Specifies the value of the editor.
	* `Editor`(`Telerik.Maui.Conrols.DataFormCustomEditor`)&mdash;Gets the editor this control is associated with.

* `Placeholder`(`string`)&mdash;Specifies the placeholder value to display, when there hasn't been input in the editor.
* `PropertyName`(`string`)&mdash;Specifies the name of the property from the business object this editor is bound to.
* `PropertyValue`(`object`)&mdash;Defines the value of the property from the business object this editor is bound to.
* `EditorValue`(`object`)&mdash;Specifies the current edited value, before applying it to the business object.
* `IsReadOnly`(`bool?`)&mdash;Specifies whether the current editor is in a read-only mode.
* `ValidationMode`(`Telerik.Maui.Controls.DataFormValidationMode`)&mdash;Defines the current validation mode of the DataForm editor.
* `CommitMode`(`Telerik.Maui.Controls.DataFormCommitMode`)&mdash;Specifies the current commit mode of the DataForm editor.
* `ColumnSpacing`(`double`)&mdash;Specifies the horizontal spacing between the rows in the editor.
* `RowSpacing`(`double`)&mdash;Specifies the vertical spacing between the rows in the editor.
* `ErrorDisplayOptions`(`Telerik.Maui.Controls.DataFormErrorDisplayOptions?`)&mdash;Specifies the display options of the header.
* `ErrorLength`(`Microsoft.Maui.GridLength`)&mdash;Specifies the length of the error in the editor. This property has an effect only when the `Telerik.Maui.Controls.DataFormEditor.ErrorPosition` property is set to `Beside`.
* `ErrorPosition`(`Telerik.Maui.Controls.DataFormErrorPosition?`)&mdash;Specifies the error position in the editor.
* `ErrorImageSource`(`Telerik.Maui.Controls.ImageSource`)&mdash;Specifies the image source of the error icon.

**AutoComplete control as a Custom Editor**

<snippet id='dataform-custom-editor'/>

And the `ViewModel` used for the `RadDataForm`:

<snippet id='dataform-custom-editor-viewmodel'/>

Note that `local` in the snippet above points to the namespace where the `CustomEditorViewModel` is defined.

## Styling 

You can style the custom editor area by setting the `BackgroundColor`, `BorderColor` and `BorderThickness` properties.

## Inherited Editor

You can create an inherited editor that inherits from `DataFormCustomEditor`.

## See Also

- [Editors]({%slug dataform-editors%})