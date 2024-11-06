---
title: Implementing Custom Localization in .NET MAUI DataForm through Validation Attributes
description: Learn how to create and apply custom localization values for the .NET MAUI DataForm component to customize validation error messages.
type: how-to
page_title: Customizing Localization for Validation Messages in .NET MAUI DataForm when using data annotations
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

When working with the [DataForm](https://docs.telerik.com/devtools/maui/controls/dataform/overview) for .NET MAUI, you might need to customize the error messages displayed for validation errors. For example, you want to change the default range validation error message or required error message to a custom one. 

This KB article also answers the following questions:
- How to customize error messages in .NET MAUI DataForm when validation is implemented through attributes in your ViewModel?
- How to change the validation error messages in DataForm through validation attributes?

## Solution

When you use data annotations in your ViewModel for validation, such as "Required", for example:

```C#
public class MyViewModel
{
    [Required]
    public string MyProperty { get; set; }
}
```

In that case, the validation error message is provided by the attribute itself. If you have not specified your own error message explicitly, a default one is provided by the .NET framework.

You can provide your own custom error message instead:

```C#
public class MyViewModel
{
    [Required(ErrorMessage = "My custom error message.")]
    public string MyProperty { get; set; }
}
```

Likewise, if you have your own localization resources, you can localize the error message:

```C#
public class MyViewModel
{
    [Required(ErrorMessageResourceType = typeof(MyLocalizationResources),
              ErrorMessageResourceName = nameof(MyLocalizationResources.MyCustomErrorMessage))]
    public string MyProperty { get; set; }
}
```

For more information on validation attributes, refer to the [ValidationAttribute Class](https://learn.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.validationattribute?view=net-8.0) in the Microsoft documentation.

## See Also

- [DataForm Overview](https://docs.telerik.com/devtools/maui/controls/dataform/overview)
- [ValidationAttribute Class](https://learn.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.validationattribute?view=net-8.0)
