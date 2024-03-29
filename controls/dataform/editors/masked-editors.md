---
title: Masked Editors
page_title: .NET MAUI DataForm Documentation - Masked Editors
description: Learn more about the masked editors that the Telerik UI for .NET MAUI DataForm control provides.
position: 1
slug: dataform-masked-editors
---

# .NET MAUI DataForm Masked Editors

You can use the following Masked Editors the DataForm provides:

* `DataFormRadTextMaskedEditor`&mdash;Of type [`RadTextMaskedEntry`]({%slug maskedentry-text-mask%})
* `DataFormRadNumericMaskedEditor` &mdash;Of type [`RadNumericMaskedEntry`]({%slug maskedentry-numeric-mask%})
* `DataFormRadEmailMaskedEditor` &mdash;Of type [`RadEmailMaskedEntry`]({%slug maskedentry-email-mask%})
* `DataFormRadRegexMaskedEditor` &mdash;Of type [`RadRegexMaskedEntry`]({%slug maskedentry-regex-mask%})

Each Masked Editor has `Mask` and `Culture` `Placeholder` properties.

Other properties that are common for all editors are listed in the [Editors Overview]({%slug dataform-editors%}#common-properties) article.

## Styling 

You can style the editors using the properties `BackgroundColor`, `BorderColor` and `BorderThickness`. You can additionally style each editor by applying a style with the same target type as the underlying control.

A table with all editors and their control types is available in the [Editors Overview article]({%slug dataform-editors%}).

Example with `DataFormRadTextMaskedEditor`

```XAML
<Style x:Key="RadTextMaskedEditorStyle" TargetType="telerik:RadTextMaskedEntry">
             <Setter Property="EntryCornerRadius"
                Value="3" />
             <Setter Property="EntryBackgroundColor"
                Value="LightSlateGrey" />
             <Setter Property="ClearButtonColor"
                 Value="DarkOrange" />
</Style>
```

And the editor definition

```XAML
<telerik:DataFormRadTextMaskedEditor PropertyName="Password"
                                     HeaderText="Password"
                                     BackgroundColor="LightGray"
                                     BorderColor="DarkBlue"
                                     BorderThickness="1"
                                     EditorStyle="{StaticResource RadTextMaskedEditorStyle}"/>
```

For more information about how to style the editors, review the [Editors Styling article]({%slug dataform-editors-styling%}).

## See Also

- [Editors]({%slug dataform-editors%})