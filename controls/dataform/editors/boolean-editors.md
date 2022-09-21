---
title: Boolean Editors
page_title: .NET MAUI DataForm Documentation | Boolean Editors
description: "Check our &quot;Boolean Editors&quot; documentation article for Telerik DataForm for .NET MAUI control."
position: 3
slug: dataform-boolean-editors
---

# .NET MAUI DataForm Boolean Editors

You can use the following Boolean Editors the DataForm provides:

* `DataFormRadCheckBoxEditor` &mdash;of type `RadCheckBox`({%slug checkbox-overview%})
* `DataFormSwitchEditor`&mdash;of type `.NET MAUI Switch`


## Styling 

You can easily style the editors using the properties BackgroundColor, BorderColor and BorderThickness. You can additionally style each editor by applying a style with the same target type as the underlying control.

A table with all editors and their control types is available in the [Editors Overview article]({%slug dataform-editors%}).

**Example with DataFormRadCheckBoxEditor**

```XAML
<telerik:DataFormRadCheckBoxEditor PropertyName="Visited"
                                   HeaderText="Visited before"
                                   EditorStyle="{StaticResource CheckBoxStyle}" />
```

**Define the `CheckBoxStyle` for the RadCheckBox editor**

<snippet id='dataform-editors-stlying-checkbox-style' />

For more information about how to style the editors, review the [Editors Styling article]({%slug dataform-editors-styling%}).