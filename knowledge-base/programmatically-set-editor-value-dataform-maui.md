---
title: Setting Editor Value Programmatically in DataForm for UI for .NET MAUI
description: Learn how to programmatically set the value of a specific editor in the DataForm for UI for .NET MAUI.
type: how-to
page_title: Programmatically Set Editor Value in UI for .NET MAUI DataForm
meta_title: Programmatically Set Editor Value in UI for .NET MAUI DataForm
slug: programmatically-set-editor-value-dataform-maui
tags: dataform, editorgenerated, set-value, ui-for-dotnet-maui
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 11.0.1 | DataForm for .NET MAUI | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I want to programmatically set the value of a specific editor in the DataForm for UI for .NET MAUI. My editors are generated using the `OnEditorGenerated` event.

This knowledge base article also answers the following questions:
- How can I set a value to a DataForm editor programmatically?
- How to use the EditorGenerated event in DataForm for UI for .NET MAUI?
- How to bind model properties to DataForm editors?

## Solution

To programmatically set the value of a specific editor in the DataForm for UI for .NET MAUI, assign the desired value to the corresponding property in the bound model. The editor reflects the value automatically when the binding is active.

1. Bind the DataForm to a model using its `BindingContext`.
2. Update the property in the model to programmatically set the editor value.
3. Use the `OnEditorGenerated` event to customize the editor during its creation.

```csharp
public partial class MainPage : ContentPage
{
    GettingStartedModel vm;
    public MainPage()
    {
        InitializeComponent();

        // Initialize the model and bind it to the DataForm
        this.vm = new GettingStartedModel();
        this.dataForm.BindingContext = this.vm;

        // Handle the EditorGenerated event
        this.dataForm.EditorGenerated += this.OnEditorGenerated;
    }

    private void OnEditorGenerated(object sender, DataFormEditorGeneratedEventArgs eventArgs)
    {
        // Customize the editor based on the property name
        switch (eventArgs.PropertyName)
        {
            case "People":
                eventArgs.Editor.HeaderText = "Number of People";
                break;
        }
    }
}

// Model with a property bound to the DataForm editor
public class GettingStartedModel : NotifyPropertyChangedBase
{
    private double? people = 1;

    [Display(Name = "Number of People")]
    public double? People
    {
        get => this.people;
        set => this.UpdateValue(ref this.people, value);
    }
}
```

## See Also

- [UI for .NET MAUI DataForm Overview](https://docs.telerik.com/devtools/maui/controls/dataform/overview)
- [UI for .NET MAUI DataForm Editor Properties](https://docs.telerik.com/devtools/maui/controls/dataform/editors/overview#common-properties-for-built-in-editors)
