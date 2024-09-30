---
title: Implementing Custom Localization in .NET MAUI DataForm
description: Learn how to create and apply custom localization values for the .NET MAUI DataForm component to customize validation error messages.
type: how-to
page_title: Customizing Localization for Validation Messages in .NET MAUI DataForm
slug: custom-localization-dotnet-maui-dataform
tags: dataform, .net maui, localization, validation, custom error message
res_type: kb
ticketid: 1663273
---

## Environment

<table>
<tbody>
<tr>
<td>Product</td>
<td>DataForm for .NET MAUI</td>
</tr>
<tr>
<td>Version</td>
<td>7.0.0</td>
</tr>
</tbody>
</table>

## Description

When working with the [DataForm](https://docs.telerik.com/devtools/maui/controls/dataform/overview) for .NET MAUI, you might need to customize the error messages displayed for validation errors. Specifically, you want to change the default range validation error message to a custom one. 

This KB article also answers the following questions:
- How to customize error messages in .NET MAUI DataForm?
- How to use custom localization with DataForm in .NET MAUI?
- How to change the validation error messages in DataForm?

## Solution

To customize the error messages in the DataForm component, create a custom localization manager by extending the `TelerikLocalizationManager` class. Override the `GetString` method to return custom messages for specific keys. 

Here is how to implement a custom localization manager:

```csharp
public class CustomTelerikLocalizationManager : TelerikLocalizationManager
{
    public override string GetString(string key)
    {
        if (key == "DataForm_RangeValidationError")
        {
            return "My error message";
        }

        return base.GetString(key);
    }
}
```

After implementing the custom localization manager, assign it to the `TelerikLocalizationManager.Manager` property before initializing the components:

```csharp
TelerikLocalizationManager.Manager = new CustomTelerikLocalizationManager();
InitializeComponent();
```

### Defining Validation Rules

There are two ways to define validation rules for properties in the DataForm:

1. **Using Built-in Validation Classes**

Specify validation rules directly in XAML:

```xml
<telerik:DataFormCustomEditor.ValidationRules>
    <telerik:DataFormEditorRangeValidationRule Minimum="0" Maximum="1000000" />
</telerik:DataFormCustomEditor.ValidationRules>
```

2. **Using Validation Attributes in Your ViewModel**

Specify validation rules using data annotations:

```csharp
[Required]
[Range(0, 1000000, ErrorMessage = "My error message")]
public int? Population
{
    get => population;
    set => UpdateValue(ref population, value);
}
```

For more information on validation attributes, refer to the [ValidationAttribute Class](https://learn.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.validationattribute?view=net-8.0) in the Microsoft documentation.

## See Also

- [DataForm Overview](https://docs.telerik.com/devtools/maui/controls/dataform/overview)
- [ValidationAttribute Class](https://learn.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.validationattribute?view=net-8.0)
