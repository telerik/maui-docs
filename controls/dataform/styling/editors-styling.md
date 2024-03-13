---
title: Editors Styling
page_title: .NET MAUI DataForm Documentation - Editors Styling
description: Review the available Styling options which DataForm for .NET MAUI control provides for its editors.
position: 1
slug: dataform-editors-styling
---

# .NET MAUI DataForm Editors Styling

The DataForm control for .NET MAUI provides styling options for customizing the appearance of its editors. You have to apply a style to each editor individually.

Each editor provides the following properties:

* `BackgroundColor`&mdash;Defines the background color of the editor.
* `BorderColor`&mdash;Defines the border color of the editor.
* `BorderThickness`&mdash;Specifies the border thickness of the editor.
* `EditorStyle` (`Style` with `TargetType` depending on the input control which the editor uses). For example, the target type of the `RadCheckBoxEditor` is `RadCheckBox`.

## Example

The example shows how to style the DataForm 

**1.** Define the `RadDataForm` and the editors:

<snippet id='dataform-editors-styling' />

**2.** Define the `CheckBoxStyle` for the `DataFormRadCheckBoxEditor`:

<snippet id='dataform-editors-stlying-checkbox-style' />

**3.** Add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**4.** The `ViewModel` used for the DataForm editors:

<snippet id='dataform-editors-model'/>

where the `local` points to the namespace where the `EditorsViewModel` is defined.

The following image shows what the DataForm control looks like when the styles described above are applied:

![.NET MAUI DataForm Editor Styling](../images/dataform-editor-styling.png)

> For a runnable example with the DataForm Editors Styling scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **DataForm > Styling** category.

## See Also

- [Groups Styling]({%slug dataform-group-styling%})
- [Error Message Styling]({%slug dataform-error-message-styling%})
- [Validation Styling]({%slug dataform-validation-styling%})
- [Header Styling]({%slug dataform-header-styling%})