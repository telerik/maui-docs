---
title: Limiting Characters in Entry and ComboBox Controls in UI for .NET MAUI
description: Learn how to limit the number of characters entered in Telerik MAUI Entry and RadComboBox controls while typing.
type: how-to
page_title: Restricting Input Length in Entry and RadComboBox for UI for .NET MAUI
meta_title: Restricting Input Length in Entry and RadComboBox for UI for .NET MAUI
slug: restricting-input-length-entry-radcombobox-maui
tags: datagrid, ui for .net maui, entry, combobox, maxlength, textchanged
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 12.0.0 | Telerik UI for .NET MAUI Entry | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 
| 12.0.0 | Telerik UI for .NET MAUI ComboBox| [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to restrict the number of characters typed in an Entry or ComboBox control in UI for .NET MAUI applications.

This knowledge base article also answers the following questions:
- How to set a maximum character limit in Telerik MAUI Entry?
- How to access ComboBox's input and set character restrictions?
- How can I handle text changes in ComboBox or Entry?

## Solution for MAUI Entry

The [Telerik MAUI Entry](https://www.telerik.com/maui-ui/documentation/controls/entry/overview) control provides a `MaxLength` property to define the maximum number of characters allowed. It also supports a `TextChanged` event to track text changes.

```xml
<telerik:RadEntry MaxLength="10" TextChanged="OnTextChanged" />
```

## Solution for MAUI ComboBox

The [ComboBox](https://www.telerik.com/maui-ui/documentation/controls/combobox/overview) uses the `RadTextInput` control for text input when in editable mode. You can access `RadTextInput` through the `Loaded` event of `RadComboBox` and set the `MaxLength` property.

```xml
<VerticalStackLayout>
    <telerik:RadComboBox ItemsSource="{Binding Locations}"
                         DisplayMemberPath="City"
                         IsEditable="True" 
                         x:Name="combo"
                         Loaded="RadComboBox_Loaded" />
</VerticalStackLayout>
```

In the code-behind, access `RadTextInput` and define the character limit:

```csharp
private void RadComboBox_Loaded(object sender, EventArgs e)
{
    var textInput = ChildOfType<RadTextInput>(this.combo);
    textInput.MaxLength = 4;
    textInput.TextChanged += TextInput_TextChanged;
}

private void TextInput_TextChanged(object? sender, TextChangedEventArgs e)
{
    // Handle text changes if needed.
}

internal static T ChildOfType<T>(View visualElement) where T : View
{
    if (visualElement == null)
    {
        return null;
    }
    foreach (var item in VisualTreeElementExtensions.GetVisualTreeDescendants(visualElement))
    {
        if (item is T targetElement)
        {
            return targetElement;
        }
    }
    return null;
}
```


## See Also

- [Entry Overview](https://www.telerik.com/maui-ui/documentation/controls/entry/overview)
- [ComboBox Overview](https://www.telerik.com/maui-ui/documentation/controls/combobox/overview)
- [Text Input Documentation](https://www.telerik.com/maui-ui/documentation/controls/entry/text-input)
- [Entry Events Documentation](https://www.telerik.com/maui-ui/documentation/controls/entry/events)
