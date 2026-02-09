---
title: Validation
page_title: .NET MAUI Editor Documentation - Validation
description: Learn what are the validation options available in the Telerik UI for .NET MAUI Editor control.
position: 4
slug: editor-validation
---

# .NET MAUI Editor Validation

The Telerik UI for .NET MAUI editor control provides validation mechanism. If the user is entering a value not matching the requirements, the Editor will display an error message, which you can customize.

@[template](/_contentTemplates/controls/inputview.md#inputview-validation)

![Editor validation](images/editor_ReserveSpaceForErrorView_property.png)

Here is an example of how to use the validation properties:

```XAML
<telerik:RadEditor ValidationErrorMessage="Value is not valid"
				   IsValueValid="False"
				   Placeholder="Enter text here"
				   PlaceholderColor="#99000000" />
```

And the namespace used:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

## Styling the Error View

@[template](/_contentTemplates/controls/inputview.md#inputview-validation-style)

>tip For a runnable example demonstrating the Editor's Validation styling, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **Editor > Styling** category.

## See Also

- [Text Appearance]({%slug editor-text-appearance%})
- [Text Selection]({%slug editor-text-selection%})
- [Events]({%slug editor-events%})
- [Styling]({%slug editor-styling%})
- [Visual States]({%slug editor-visual-states%})
