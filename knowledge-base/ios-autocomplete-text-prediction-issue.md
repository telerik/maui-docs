---
title: Disabling iOS Auto-Correction in RadAutoComplete for Correct Text Selection
description: Fixing the issue where iOS auto-correction inserts incorrect text instead of selected items in RadAutoComplete.
type: how-to
page_title: Resolving Incorrect Text Issue in iOS RadAutoComplete
meta_title: Resolving Incorrect Text Issue in iOS RadAutoComplete
slug: ios-autocomplete-text-prediction-issue
tags: autocomplete, ios, text-prediction, istextpredictionenabled
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.0.1 | AutoComplete for .NET MAUI | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

When using [AutoComplete](https://docs.telerik.com/devtools/maui/controls/autocomplete/overview) on iOS, the auto-correction feature causes unexpected behavior during suggestion selection. Instead of inserting the selected item, iOS auto-correction inserts an auto-completed string, such as "Er". This issue occurs specifically when iOS automatically highlights its auto-correction suggestions.

This knowledge base article also answers the following questions:
- How to disable iOS auto-correction for `RadAutoComplete`?
- Why does incorrect text appear in `RadAutoComplete` selection on iOS?
- How to resolve text prediction issues in RadAutoComplete?

## Solution

Disable the iOS auto-correction feature to ensure the correct item is inserted upon selection. The `RadAutoComplete` uses the `RadTextInput` control internally, which inherits from the Microsoft MAUI Entry control. You can set the `IsTextPredictionEnabled` property of the `RadTextInput` to `False` using the `TextInputStyle` property of RadAutoComplete.

1. Define a style for RadTextInput in the `ResourceDictionary`.
2. Set the `IsTextPredictionEnabled` property to `False` in the style.
3. Apply the style to the `TextInputStyle` property of RadAutoComplete.

```xaml
<ContentPage.Resources>
    <ResourceDictionary>
        <Style x:Key="myStyle" TargetType="telerik:RadTextInput">
            <Setter Property="IsTextPredictionEnabled" Value="False"/>
        </Style>
    </ResourceDictionary>
</ContentPage.Resources>

<VerticalStackLayout>
    <telerik:RadAutoComplete TextInputStyle="{StaticResource myStyle}" />
</VerticalStackLayout>
```

This configuration disables text prediction and auto-correction, ensuring the selected item is correctly inserted.

## See Also

- [AutoComplete Overview](https://docs.telerik.com/devtools/maui/controls/autocomplete/overview)
- [TextInput Documentation](https://docs.telerik.com/devtools/maui/controls/entry/text-input)
