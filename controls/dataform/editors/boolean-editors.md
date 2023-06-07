---
title: Boolean Editors
page_title: .NET MAUI DataForm Documentation - Boolean Editors
description: "Check our &quot;Boolean Editors&quot; documentation article for Telerik DataForm for .NET MAUI control."
position: 3
slug: dataform-boolean-editors
---

# .NET MAUI DataForm Boolean Editors

You can use the following Boolean Editors the DataForm provides:

* `DataFormRadCheckBoxEditor` &mdash;Of type [`RadCheckBox`]({%slug checkbox-overview%}). Using the `IsThreeState` porperty of type `bool?` you can specify whether the CheckBox editor will have three states - true, false, indeterminate.
* `DataFormSwitchEditor`&mdash;Of type `.NET MAUI Switch`.

Other properties that are common for all editors are listed in the [Editors Overview]({%slug dataform-editors%}#common-properties) article.

## Styling 

You can easily style the editors using the properties BackgroundColor, BorderColor and BorderThickness. You can additionally style each editor by applying a style with the same target type as the underlying control.

**Example with DataFormRadCheckBoxEditor**

```XAML
<telerik:DataFormRadCheckBoxEditor PropertyName="Visited"
                                   HeaderText="Visited before"
                                   EditorStyle="{StaticResource CheckBoxStyle}" />
```

**Define the `CheckBoxStyle` for the RadCheckBox editor**

<snippet id='dataform-editors-stlying-checkbox-style' />

For more information about how to style the editors, review the [Editors Styling article]({%slug dataform-editors-styling%}).

## See Also

- [Editors]({%slug dataform-editors%})