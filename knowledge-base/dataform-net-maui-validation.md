---
title: Implementing Validation in DataForm for .NET MAUI
description: Learn how to add validation rules to your DataForm fields in .NET MAUI by using Data Annotations.
type: how-to
page_title: How to Add Validation to DataForm in .NET MAUI Using Data Annotations
slug: dataform-net-maui-validation
tags: dataform, .net maui, validation, data annotations, regex
res_type: kb
---

## Environment

| Versions | Product | Author | 
| --- | --- | ---- | 
| 9.0.0 | Telerik UI for .NET MAUI DataForm | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

When working with DataForm in .NET MAUI, there might be requirements to validate the input data, such as checking if an entry is a valid email address or phone number. The question arises on how to implement these validations without manually coding standard inputs for each field type.

This knowledge base article also answers the following questions:
- How to validate phone numbers in DataForm?
- How to validate email addresses in DataForm?
- How to use regular expressions for validation in DataForm?

## Solution

To enable validation in the DataForm for .NET MAUI, utilize the data annotations provided by the `System.ComponentModel.DataAnnotations` namespace. These annotations can trigger validation on various events such as lost focus, property changed, or manually. 

Here are examples on how to apply different validation rules:

### Validating a Phone Number

To validate a phone number, use the `[Phone]` attribute along with a `[RegularExpression]` attribute for more specific patterns. 

```csharp
[Required]
[Phone]
[RegularExpression(pattern: "(?:(?:\\+?1\\s*(?:[.-]\\s*)?)?(?:(\\s*([2-9]1[02-9]|[2-9][02-8]1|[2-9][02-8][02-9]‌​)\\s*)|([2-9]1[02-9]|[2-9][02-8]1|[2-9][02-8][02-9]))\\s*(?:[.-]\\s*)?)([2-9]1[02-9]‌​|[2-9][02-9]1|[2-9][02-9]{2})\\s*(?:[.-]\\s*)?([0-9]{4})(?:\\s*(?:#|x\\.?|ext\\.?|extension)\\s*(\\d+))?$", ErrorMessage = "Invalid phone format")]
[Display(Name = "Phone", Prompt = "Enter Phone")]
public string Phone
{
    get => this.phone;
    set => this.UpdateValue(ref this.phone, value);
}
```

### Validating an Email Address

For email address validation, the `[EmailAddress]` attribute is sufficient. This ensures the input matches a basic email pattern.

```csharp
[Required]
[EmailAddress]
[Display(Name = "Email", Prompt = "Enter Email")]
public string Email
{
    get => this.email;
    set => this.UpdateValue(ref this.email, value);
}
```

### Note on Regular Expressions

Regular expressions (regex) offer a powerful way to specify validation patterns. In the example above, the regex is used to validate a phone number format. Be mindful that complex patterns can be difficult to read and maintain, so test extensively.

## See Also

- [Data Annotations in .NET MAUI DataForm](https://docs.telerik.com/devtools/maui/controls/dataform/data-annotations)
- [System.ComponentModel.DataAnnotations Namespace](https://learn.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations?view=net-9.0)
- [Regular Expression Language - Quick Reference](https://learn.microsoft.com/en-us/dotnet/standard/base-types/regular-expression-language-quick-reference)
