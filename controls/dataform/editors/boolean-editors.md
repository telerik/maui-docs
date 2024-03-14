---
title: Boolean Editors
page_title: .NET MAUI DataForm Documentation - Boolean Editors
description: Learn more about the boolean editors that the Telerik UI for .NET MAUI DataForm control provides.
position: 3
slug: dataform-boolean-editors
---

# .NET MAUI DataForm Boolean Editors

You can use the following Boolean Editors the DataForm provides:

* `DataFormRadCheckBoxEditor` &mdash;Of type [`RadCheckBox`]({%slug checkbox-overview%}). Using the `IsThreeState` property of type `bool?` you can specify whether the CheckBox editor will have three states—true, false, indeterminate.
* `DataFormSwitchEditor`&mdash;Of type `.NET MAUI Switch`.

Other properties that are common for all editors are listed in the [Editors Overview]({%slug dataform-editors%}#common-properties) article.

## Styling 

You can style the editors using the properties `BackgroundColor`, `BorderColor` and `BorderThickness`. You can additionally style each editor by applying a style with the same target type as the underlying control.

Example with `DataFormRadCheckBoxEditor`

<snippet id='dataform-editors-styling' />

Define the `CheckBoxStyle` for the `RadCheckBox` editor

<snippet id='dataform-editors-stlying-checkbox-style' />


> For a runnable example with the DataForm Editors Styling, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **DataForm > Styling** category.

## See Also

- [Editors]({%slug dataform-editors%})