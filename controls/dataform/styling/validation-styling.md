---
title: Validation Styling
page_title: .NET MAUI DataForm Documentation - Validation Styling
description: Review the available styling options which DataForm for .NET MAUI control provides when validating its data.
position: 4
slug: dataform-validation-styling
---

# .NET MAUI DataForm Validation Styling

You can customize the validation look using the following styling properties:

* `ValidationSummaryStyle`(of type `Style` with target type `DataFormValidationSummaryView`)&mdash;Defines the style of the validation summary view.
* `ValidationSummaryLabelStyle`(of type `Style` with target type `Label`)&mdash;Defines the validation summary label style.
* `ValidationSummaryImageStyle`(of type `Style` with target type `Image`)&mdash;Defines the validation summary image style.

## Example

The following examples demonstrate how to style the DataForm validation summary.

**1.** Define the `RadDataForm`:

<snippet id='dataform-validation-style' />

Note that `local` in the snippet above points to the namespace where the `EditorsViewModel` is defined.

**2.** Define the `ValidationSummaryStyle`:

<snippet id='dataform-validation-summary-style' />

**3.** Define the `ValidationLabelStyle`:

<snippet id='dataform-validation-label-style' />

**4.** Add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**5.** Define the `ViewModel` used as a `BindingContext` for the `RadDataForm`:

<snippet id='dataform-editors-model'/>

The following image shows what the DataForm control looks like when the styles described above are applied:

![.NET MAUI DataForm Validation Styling](../images/dataform-validation-styling.png)

> For a runnable example with the DataForm Validation Styling scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **DataForm > Styling** category.

## See Also

- [Editors Styling]({%slug dataform-editors-styling%})
- [Groups Styling]({%slug dataform-group-styling%})
- [Error Message Styling]({%slug dataform-error-message-styling%})
- [Header Styling]({%slug dataform-header-styling%})