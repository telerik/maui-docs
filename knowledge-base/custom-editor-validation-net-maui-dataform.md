---
title: Implementing Custom Editor Validation in .NET MAUI DataForm
description: Learn how to apply custom validation rules to custom editors in the .NET MAUI DataForm component using the EditorGenerated event.
type: how-to
page_title: Custom Validation for .NET MAUI DataForm Editors
slug: custom-editor-validation-net-maui-dataform
tags: dataform, .net maui, validation, custom editor, editorgenerated
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 10.1.0 | Telerik UI for .NET MAUI DataForm | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

I have a DataForm and I want to apply custom validation on custom editors using the `EditorGenerated` event. 

This knowledge base article also answers the following questions:
- How to implement custom validation for DataForm editors in .NET MAUI?
- How to use the `EditorGenerated` event for custom editor validation?
- How to create custom validation rules for .NET MAUI DataForm component?

## Solution

To apply custom validation to editors in the .NET MAUI DataForm, follow these steps:

1. Define the DataForm in XAML and subscribe to the `EditorGenerated` event.

```xaml
<telerik:RadDataForm x:Name="formulaireForm" 
                     Grid.Row="1" EditorGenerated="OnEditorGenerated"
                     AutoGenerateItems="True"
                     IsValidationSummaryVisible="True"
                     CommitMode="PropertyChanged"
                     ValidationMode="PropertyChanged">
    <telerik:RadDataForm.LayoutDefinition>
        <telerik:DataFormGridLayout ColumnCount="{OnIdiom Phone='1', Desktop='1', Tablet='3'}"
                                RowSpacing="15"
                                ColumnSpacing="5"/>
    </telerik:RadDataForm.LayoutDefinition>
</telerik:RadDataForm>
```

2. Implement the `ViewModel` with the corresponding properties and the `ValidateStartDate` and `ValidateText` custom validation methods.

```csharp
public class GettingStartedModel : NotifyPropertyChangedBase
{
    private string firstName;
    private DateTime? startDate;

    [Display(Name = "First Name")]
    public string FirstName
    {
        get => this.firstName;
        set => this.UpdateValue(ref this.firstName, value);
    }

    [Display(Name = "Star date")]
    public DateTime? StartDate
    {
        get => this.startDate;
        set => this.UpdateValue(ref this.startDate, value);
    }

    public ValidationResult ValidateStartDate(object value, ValidationContext context)
    {
        var startDate = (DateTime?)value;
        if (startDate is null) return new ValidationResult("Start Date is required.");
        if (startDate < DateTime.Today) return new ValidationResult("Start Date cannot be in the past.");
        return ValidationResult.Success;
    }

    public ValidationResult ValidateText(object value, ValidationContext context)
    {
        var enterText = (string)value;
        if (enterText is null || enterText.Length == 0) return new ValidationResult("Text cannot be null");
        if (enterText.Length < 5) return new ValidationResult("Enter more than 5 symbols");
        return ValidationResult.Success;
    }
}
```

3. In the `MainPage`, define the editors and set their custom validation rules in the `OnEditorGenerated` event handler.

```csharp
public partial class MainPage : ContentPage
{
    GettingStartedModel vm;
    public MainPage()
    {
        InitializeComponent();
        this.vm = new GettingStartedModel();
        this.BindingContext = this.vm;
    }

    private void OnEditorGenerated(object sender, DataFormEditorGeneratedEventArgs eventArgs)
    {
        var editor = (ControlTemplate)this.Resources["CustomEditorTemplate"];
        switch (eventArgs.PropertyName)
        {
            case "StartDate":
                eventArgs.Editor = new DataFormDatePickerEditor()
                {
                    PropertyName = "StartDate",
                };
                eventArgs.Editor.ValidationRules.Add(new DataFormEditorCustomValidationRule
                {
                    Validation = (this.BindingContext as GettingStartedModel).ValidateStartDate,
                });
                break;
            
            case "FirstName":
                eventArgs.Editor = new DataFormCustomEditor()
                {
                    EditorTemplate = editor,
                };
                eventArgs.Editor.ValidationRules.Clear();
                eventArgs.Editor.ValidationRules.Add(new DataFormEditorCustomValidationRule
                {
                    Validation = (this.BindingContext as GettingStartedModel).ValidateText,
                });
                break;
        }
    }
}
```

4. Define the control template for the custom editor in XAML.

```xaml
<ControlTemplate x:Key="CustomEditorTemplate">
    <VerticalStackLayout>
        <telerik:RadEntry Text="{Binding Value, Mode=TwoWay, Source={RelativeSource Mode=TemplatedParent}}" />
    </VerticalStackLayout>
</ControlTemplate>
```

## See Also

- [DataForm Documentation](https://docs.telerik.com/devtools/maui/controls/dataform/overview)
- [Custom Editors in DataForm](https://docs.telerik.com/devtools/maui/controls/dataform/editors/custom-editor)
- [DataForm Validation](https://docs.telerik.com/devtools/maui/controls/dataform/validation)
