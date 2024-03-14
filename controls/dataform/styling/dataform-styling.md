---
title: DataForm Styling
page_title: .NET MAUI DataForm Documentation - DataForm Styling
description: Review the available Styling options which DataForm for .NET MAUI control provides.
position: 0
slug: dataform-styling
---

# .NET MAUI DataForm Styling

The DataForm control for .NET MAUI provides styling options for customizing its appearance. You can style the DataForm itself, as well as its editors, groups, error messages and validation messages.

The control supports the following styling properties:

* `BackgroundColor`&mdash;Defines the background color of the DataForm.
* `BorderColor`&mdash;Defines the border color of the DataForm.
* `BorderThickness`&mdash;Specifies the border thickness of the DataForm.

The following example demonstrate how to use the styling properties of the DataForm:

<snippet id='dataform-styling' />

Note that `local` in the snippet above points to the namespace where the `DataTypeEditorsModel` is defined.

Define the `ViewModel` used as a `BindingContext` for the DataForm:

<snippet id='dataform-datatype-editors-model'/>

![.NET MAUI DataForm Styling](../images/dataform-style.png)

> For a runnable example with the DataForm Styling scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **DataForm > Styling** category.

## See Also

- [Editors Styling]({%slug dataform-editors-styling%})
- [Groups Styling]({%slug dataform-group-styling%})
- [Error Message Styling]({%slug dataform-error-message-styling%})
- [Validation Styling]({%slug dataform-validation-styling%})
- [Header Styling]({%slug dataform-header-styling%})