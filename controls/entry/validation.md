---
title: Validation
page_title: .NET MAUI Entry Documentation - Validation
description: Learn what are the validation options available in the Telerik UI for .NET MAUI Entry control.
position: 4
slug: entry-validation
---

# .NET MAUI Entry Validation

The Telerik UI for .NET MAUI entry control provides validation mechanism. If the user is entering a value not matching the requirements, the Entry will display an error message, which you can customize.

@[template](/_contentTemplates/controls/inputview.md#inputview-validation)

![Entry validation](images/entry_ReserveSpaceForErrorView_property.png)

Here is an example of how to use the validation properties:

```XAML
<telerik:RadEntry ValidationErrorMessage="Value is not valid"
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

## See Also

- [Text Appearance]({% slug entry-text-appearance%})
- [Text Selection]({%slug entry-text-selection %})
- [Events]({% slug entry-events%})
