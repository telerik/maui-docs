---
title: Editors Styling
page_title: .NET MAUI DataForm Documentation | Editors Styling
description: "Review the available Styling options which DataForm for .NET MAUI control provides for its editors."
position: 1
slug: dataform-editors-styling
---

# .NET MAUI Editors Styling

The DatePicker control for .NET MAUI provides styling options for customizing the apperance of its editors. You have to apply a style to each editor individually.

Each editor provides the following properties:

* `BackgroundColor`&mdash;Defines the background color of the editor.
* `BorderColor`&mdash;Defines the border color of the editor.
* `BorderThickness`&mdash;Specifies the border thickness of the editor.
* `EditorStyle` (`Style` with `TargetType` depending on the input control which the editor uses). For example, the target type of the RadCheckBoxEditor is RadCheckBox.

## Example

The example shows how to style the DataForm 

**Define the `RadDataForm` and the editors**.

<snippet id='dataform-editors-styling' />

**Define the `CheckBoxStyle` for the RadCheckBox editor**

<snippet id='dataform-editors-stlying-checkbox-style' />

Add the following namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

The following image shows what the DataForm control looks like when the styles described above are applied:

![.NET MAUI DataForm Editor Styling](../images/dataform-editor-styling.png)