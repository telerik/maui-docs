---
title: Applying Custom Validation in .NET MAUI DataForm Editors
description: Learn how to implement custom validation for built-in editors within the .NET MAUI DataForm component.
type: how-to
page_title: Custom Validation for .NET MAUI DataForm Editors
slug: custom-validation-net-maui-dataform
tags: dataform, .net maui, validation, custom validation, editors
res_type: kb
---

## Environment

| Version | Product | Author | 
| --- | --- | ---- | 
| 10.1.0 | Telerik UI for .NET MAUI DataForm | [Dobrinka Yordanova](https://www.telerik.com/blogs/author/dobrinka-yordanova) | 

## Description

This knowledge base article demonstrates how to apply custom validation to the built-in editors of the .NET MAUI DataForm component. Custom validation is essential for enforcing specific rules or conditions that the built-in validation attributes might not cover.

This knowledge base article also answers the following questions:
- How can I apply custom validation to a DataForm's editors in .NET MAUI?
- What is the procedure for adding custom validation rules to my DataForm `ViewModel`?
- Is there a way to show validation errors at the DataForm level?

## Solution

This kb article provides two approaches for applying a custom validation for DataForm editors

* Custom Validation on Property Level
* Custom Validation on `ViewModel` Level

### Custom Validation on Property Level

To apply a custom validation on a property level, use the `CustomValidationAttribute`. This attribute can be applied directly to individual properties within your `ViewModel`. 

Here is an example demonstrating how to use `CustomValidationAttribute` on a property:

```csharp
private class ViewModel : NotifyPropertyChangedBase
{
    private DateTime? startDate;
    private DateTime? endDate;

    [Display(Name = "Start Date")]
    [CustomValidation(typeof(ViewModel), nameof(ValidateStartDate))]
    public DateTime? StartDate
    {
        get => this.startDate;
        set => this.UpdateValue(ref this.startDate, value);
    }

    [Display(Name = "End Date")]
    [CustomValidation(typeof(ViewModel), nameof(ValidateEndDate))]
    public DateTime? EndDate
    {
        get => this.endDate;
        set => this.UpdateValue(ref this.endDate, value);
    }

    public static ValidationResult ValidateStartDate(object value, ValidationContext context)
    {
        var startDate = (DateTime?)value;

        if (startDate is null)
        {
            return new ValidationResult("Start Date is required.");
        }

        if (startDate < DateTime.Today)
        {
            return new ValidationResult("Start Date cannot be in the past.");
        }

        return ValidationResult.Success;
    }

    public static ValidationResult ValidateEndDate(object value, ValidationContext context)
    {
        var endDate = (DateTime?)value;

        if (endDate is null)
        {
            return new ValidationResult("End Date is required.");
        }

        if (endDate < DateTime.Today)
        {
            return new ValidationResult("End Date cannot be in the past.");
        }

        return ValidationResult.Success;
    }
}
```

### Custom Validation on ViewModel Level

For validations that involve multiple properties or the entire `ViewModel`, apply the `CustomValidationAttribute` at the `ViewModel` level. This method allows for broader validation scopes, such as comparing two property values:

```csharp
[CustomValidation(typeof(ViewModel), nameof(ValidateDates))]
public class ViewModel : NotifyPropertyChangedBase
{
    private DateTime? startDate;
    private DateTime? endDate;

    [Display(Name = "Start Date")]
    public DateTime? StartDate
    {
        get => this.startDate;
        set => this.UpdateValue(ref this.startDate, value);
    }

    [Display(Name = "End Date")]
    public DateTime? EndDate
    {
        get => this.endDate;
        set => this.UpdateValue(ref this.endDate, value);
    }

    public static ValidationResult ValidateDates(object value, ValidationContext context)
    {
        var startDate = (DateTime?)context.Items[nameof(StartDate)];
        var endDate = (DateTime?)context.Items[nameof(EndDate)];

        if (startDate >= endDate)
        {
            return new ValidationResult("Start Date must be before End Date.");
        }

        return ValidationResult.Success;
    }
}
```

### Displaying Validation Errors

To display validation errors at the DataForm level, set the `IsValidationSummaryVisible` property to `True`. This configuration ensures that all validation errors are visible to the user:

```xaml
<telerik:RadDataForm IsValidationSummaryVisible="True" />
```

Alternatively, you can define custom validation rules directly in XAML, providing flexibility in specifying validation logic:

```xaml
<telerik:RadDataForm IsValidationSummaryVisible="True">
    <telerik:DataFormDatePickerEditor PropertyName="StartDate">
        <telerik:DataFormDatePickerEditor.ValidationRules>
            <telerik:DataFormEditorCustomValidationRule Validation="ValidateStartDate" />
        </telerik:DataFormDatePickerEditor.ValidationRules>
    </telerik:DataFormDatePickerEditor>
    <telerik:DataFormDatePickerEditor PropertyName="EndDate">
        <telerik:DataFormDatePickerEditor.ValidationRules>
            <telerik:DataFormEditorCustomValidationRule Validation="ValidateEndDate" />
        </telerik:DataFormDatePickerEditor.ValidationRules>
    </telerik:DataFormDatePickerEditor>
    <telerik:RadDataForm.ValidationRules>
        <telerik:DataFormObjectValidationRule Validation="ValidateDates" />
    </telerik:RadDataForm.ValidationRules>
</telerik:RadDataForm>
```

## See Also

- [.NET MAUI DataForm Documentation](https://docs.telerik.com/devtools/maui/controls/dataform/overview)
- [CustomValidationAttribute Documentation](https://learn.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.customvalidationattribute?view=net-9.0)
- [ValidationContext Documentation](https://learn.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.validationcontext?view=net-9.0)
