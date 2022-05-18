---
title: Validation
page_title: .NET MAUI Entry Documentation | Validation
description: "Learn what are the validation options available in the Telerik UI for .NET MAUI Entry control."
position: 4
slug: entry-validation
---

# Validation

The Telerik UI for .NET MAUI entry control provides validation mechanism. If the user is entering a value not matching the requirements, the Entry will display an error message, which you can easily customize.

* `IsValueValid`(`bool`)&mdash;Specifies whether the Text entered inside the control is valid. The default value is true.

* `ValidationErrorMessage`(`string`)&mdash;Specifies the the error message which is displayed when the text entered inside the control is not valid.

```XAML
<telerik:RadEntry ValidationErrorMessage="Value is not valid"
				  IsValueValid="False"
				  Placeholder="Enter text here"
				  PlaceholderColor="#99000000">
</telerik:RadEntry>
```

And the namespace used:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

## See Also

- [Text Appearance]({% slug entry-text-appearance%})
- [Text Selection]({%slug entry-text-selection %})
- [Events]({% slug entry-events%})
