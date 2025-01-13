---
title: Accessing Controls Inside a DataTemplate or ControlTemplate in .NET MAUI
description: Learn how to access and interact with controls defined within a DataTemplate or ControlTemplate in .NET MAUI applications.
type: how-to
page_title: How to Access Controls Within Templates in .NET MAUI
slug: access-controls-inside-datatemplates-net-maui
tags: .net maui, controltemplate, datatemplate, visualtree, getvisualtreedescendants
res_type: kb
---

## Environment

| Control | Author | 
| ---- | ---- | 
| Access Controls inside `DataTemplate` or `ControlTemplate` in .NET MAUI | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

In .NET MAUI, when a control is added inside a `DataTemplate` or `ControlTemplate`, it cannot be directly accessed from outside the template using its `x:Name`. This article provides a solution to access and interact with controls within a `DataTemplate` or `ControlTemplate`.

This knowledge base article also answers the following questions:
- How to interact with a control inside a `DataTemplate` or `ControlTemplate`?
- How to find a control within a template in .NET MAUI?
- How to use `GetVisualTreeDescendants()` to access controls in .NET MAUI?

## Solution

To access a control inside a `DataTemplate` or `ControlTemplate`, use the `.NET MAUI` `GetVisualTreeDescendants()` method. This method allows you to traverse through all children in the control and obtain an instance of the control inside the template.

Follow the steps below to implement the solution:

1. Use the `GetVisualTreeDescendants()` method to traverse the visual tree and find the desired control.
2. Cast the found control to the specific control type you are looking for.
3. Once you have the control instance, you can interact with it as needed.

Here is an example code snippet demonstrating how to access a control inside a template on a button click event:

```C#
private async void Button_Clicked(object sender, EventArgs e)
{
    List<IVisualTreeElement> items = (List<IVisualTreeElement>)this.MainControl.GetVisualTreeDescendants();
    foreach (IVisualTreeElement myControl in items)
    {
        if (myControl is MyControl) // Replace MyControl with your specific control type that is inside the DataTemplate or the ControlTemplate
        {
            MyControl control = (MyControl)myControl;
            // Add your logic here
            return;
        }
    }
}
```

Replace `MyControl` with the specific control type you are looking for. This approach enables you to interact with controls defined within templates in your .NET MAUI application.

## See Also

- [DataForm Overview for .NET MAUI](https://docs.telerik.com/devtools/maui/controls/dataform/overview)
- [Exploring the Visual Tree in .NET MAUI](https://docs.microsoft.com/en-us/dotnet/maui/user-interface/layouts/visual-tree)
- [Control Templates in .NET MAUI](https://docs.microsoft.com/en-us/dotnet/maui/user-interface/controls/templates)