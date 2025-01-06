---
title: Localize DataForm Display Attributes in .NET MAUI
description: Learn how to use the DisplayAttribute for localization in the Telerik .NET MAUI DataForm.
type: how-to
page_title: How to Localize Display Attributes in Telerik .NET MAUI DataForm
slug: localize-dataform-display-attributes-net-maui
tags: dataform, .net maui, localization, displayattribute, resourcetype
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 9.0.0 | Telerik UI for .NET MAUI DataForm | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova)| 

## Description

When working with the Telerik .NET MAUI DataForm, I need to localize the display names of fields using `DisplayAttribute` from data annotations. My resource files (.resx) are located in a separate assembly named `MyAssembly`. How can I achieve localization in this setup?

This knowledge base article also answers the following questions:
- How to use `DisplayAttribute` for localization in .NET MAUI DataForm?
- How to access resource files from a different assembly for localization in .NET MAUI?
- How to localize display names in .NET MAUI DataForm using `DisplayAttribute`?

## Solution

To localize display names in the Telerik .NET MAUI DataForm, utilize the `DisplayAttribute` provided by Microsoft, specifically its `ResourceType` property. This approach allows you to define your resource files (.resx) in any assembly and use them for localization.

### Steps to Localize Display Names

1. Create the Resource File.

   In your class library project (e.g., `MauiLib1`), add a .resx file. Ensure you change the access modifier of the .resx file to public so it can be accessed from your main project.

1. Reference the Resource File.

   In your main project (e.g., `MauiApp24`), you can also add a .resx file if needed. This demonstrates that the location of the resource files does not limit their use for localization.

1. Use the `DisplayAttribute` for Localization.

   In your model, apply the `DisplayAttribute` to properties you wish to localize. Specify the `Name` property with the name of the resource entry and the `ResourceType` property with the type of your resource class.

2. **Reference the Resource File**: In your main project (e.g., `MauiApp24`), you can also add a .resx file if needed. This demonstrates that the location of the resource files does not limit their use for localization.

3. **Use the `DisplayAttribute` for Localization**: In your model, apply the `DisplayAttribute` to properties you wish to localize. Specify the `Name` property with the name of the resource entry and the `ResourceType` property with the type of your resource class.

```csharp
// Uses resx file from the same project - MauiApp24
[Required]
[Display(Name = nameof(MyResources.FirstName), ResourceType = typeof(MyResources))]
public string FirstName
{
    get => this.firstName;
    set => this.UpdateValue(ref this.firstName, value);
}

// Uses a resx file from a different project - MauiLib1
[Required]
[Display(Name = nameof(ResourceTest.LastName), ResourceType = typeof(ResourceTest))]
public string LastName
{
    get => this.lastName;
    set => this.UpdateValue(ref this.lastName, value);
}
```

### Key Points
- The `ResourceType` property of the `DisplayAttribute` is essential for localization.
- Resource files can be located in the same project or a different one.
- Changing the access modifier of the .resx file to public is necessary for cross-assembly access.

## See Also

- [DataForm for .NET MAUI Documentation](https://docs.telerik.com/devtools/maui/controls/dataform/overview)
- [.NET DisplayAttribute ResourceType Property](https://learn.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute.resourcetype?view=net-7.0#system-componentmodel-dataannotations-displayattribute-resourcetype)
