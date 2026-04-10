---
title: Using Data Annotations in Telerik UI for .NET MAUI DataForm
description: Learn how to use data annotations in the Telerik UI for .NET MAUI DataForm, including setting required fields and editor placeholder text.
type: how-to
page_title: Adding Data Annotations in Telerik UI for .NET MAUI DataForm
meta_title: Adding Data Annotations in Telerik UI for .NET MAUI DataForm
slug: using-data-annotations-in-telerik-maui-dataform
tags: telerik, ui for .net maui, dataform, data annotations, required field, placeholder text
res_type: kb
---

## Environment

| Version | Product | Author |
| --- | --- | ---- |
| 13.0.0 | Telerik UI for .NET MAUI DataForm | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) |

## Description

I want to use data annotations in the [Telerik UI for .NET MAUI DataForm](https://www.telerik.com/maui-ui/documentation/controls/dataform/data-annotations). Specifically, I need to know how to mark a field as required and how to specify placeholder text for an editor.

This knowledge base article also answers the following questions:
- How to make a field required in Telerik MAUI DataForm?
- How to set a placeholder text for an editor in Telerik MAUI DataForm?
- What data annotations are available in Telerik MAUI DataForm?

## Solution

To use data annotations in the Telerik UI for .NET MAUI DataForm, follow these steps:

1. Add the `[Required]` attribute to mark a field as required. If the user tries to submit the form without filling it in, a validation error appears, and the submission is blocked.

2. Use the `[Display]` attribute to customize the editor. 
   - `Name`: Sets the editor header text.
   - `GroupName`: Defines the group name header.
   - `Prompt`: Specifies the placeholder text inside the editor.

The next example shows how to use data annotations for a required field in the .NET MAUI DataForm:

```csharp
[Required] // Marks the field as required.
[Display(Name = "First Name", 
         GroupName = "Personal Information", 
         Prompt = "enter name")] 
// Name sets the header text. 
// GroupName sets the group's header text.
// Prompt sets the placeholder text in the input area.
public string FirstName
{
    get => this.name;
    set => this.UpdateValue(ref this.name, value);
}
```

## See Also

- [Data Annotations Documentation for Telerik UI for .NET MAUI DataForm](https://www.telerik.com/maui-ui/documentation/controls/dataform/data-annotations)
- [Telerik UI for .NET MAUI DataForm Documentation](https://www.telerik.com/maui-ui/documentation/controls/dataform/overview) 
