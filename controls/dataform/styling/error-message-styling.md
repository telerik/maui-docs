---
title: Error Message Styling
page_title: .NET MAUI DataForm Documentation - Error Message Styling
description: Review the available Styling options which DataForm for .NET MAUI control provides when error messages are displayed during validation.
position: 3
slug: dataform-error-message-styling
---

# .NET MAUI DataForm Error Message Styling

The DatePicker control for .NET MAUI provides styling options for customizing the appearance of the error message that appears when the entered data is invalid.

The style of the error message can be set individually for each editor or directly to the DataForm control using the following styling properties:

* `ErrorImageSource`(`ImageSource`)&mdash;Specifies the `ImageSource` of the image displayed in the error message.
* `ErrorImageStyle`(of type `Style` with target type `Image`)&mdash;Defines the error image style.
* `ErrorLabelStyle`(of type `Style` with target type `Label`)&mdash;Defines the error label style.

**1.** Defining two different `ErrorLabelStyle`:

<snippet id='dataform-error-label-style' />
<snippet id='dataform-error-label-style-alt' />

**2.** Apply common `ErrorLabelStyle` for all editors:

<snippet id='dataform-error-label-style-common' />

**3.** Apply `ErrorLabelStyle` per editor:

<snippet id='dataform-error-label-style-individual' />

**4.** Add the following namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**5.** The `ViewModel` used for the DataForm editors

<snippet id='dataform-datatype-editors-model'/>

where the `local` points to the namespace where the `DataTypeEditorsModel` is defined.

The following image shows what the DataForm control looks like when the styles described above are applied:

![.NET MAUI DataForm Error Message Styling](../images/dataform-error-message-styling.png)

> For a runnable example with the DataForm Error Message Styling scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **DataForm > Styling** category.

## See Also

- [Editors Styling]({%slug dataform-editors-styling%})
- [Groups Styling]({%slug dataform-group-styling%})
- [Validation Styling]({%slug dataform-validation-styling%})
- [Header Styling]({%slug dataform-header-styling%})