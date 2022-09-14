---
title: Validation Styling
page_title: .NET MAUI DataForm Documentation | Validation Styling
description: "Review the available styling options which DataForm for .NET MAUI control provides when validating its data."
position: 4
slug: dataform-validation-styling
---

# .NET MAUI DataForm Validation Styling

You can easily customize the validation look using the following styling properties:

* `ValidationSummaryStyle`(of type `Style` with target type `DataFormValidationSummaryView`)&mdash;Defines the style of the validation summary view.
* `ValidationSummaryLabelStyle`(of type `Style` with target type `Label`)&mdash;Defines the validation summary label style.
* `ValidationSummaryImageStyle`(of type `Style` with target type `Image`)&mdash;Defines the validation summary image style.

##Example

The following examples demonstrate how to style the DataForm validation summary.

**Define the `RadDataForm`**

<snippet id='dataform-validation-style' />

**Define the `ValidationSummaryStyle`**

<snippet id='dataform-validation-summary-style' />

**Define the `ValidationLabelStyle`**

<snippet id='dataform-validation-label-style' />

Add the following namespace:

 ```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
 ```

The following image shows what the DataForm control looks like when the styles described above are applied:

![.NET MAUI DataForm Validation Styling](../images/dataform_validation_styling.png)