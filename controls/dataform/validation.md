---
title: Validation
page_title: .NET MAUI DataForm Documentation | Validation
description: "Check the &quot;Validation&quot; possibilities which Telerik DataForm for .NET MAUI control provides."
position: 9
slug: dataform-validation
---

# Validation

Telerik DataForm for .NET MAUI provides built-in validation, which gives you full control over the data collected through the control. 

The next sections list all DataForm members related to validation.

## Validation modes

The selected mode is applied through `ValidationMode`(of type`Telerik.Maui.Controls.DataFormValidationMode`) property of the DataForm control. You could choose between three validation modes:

* `Explicit`&mdash;The changes are validated explicitly by invoking the `ValidateCommand` or calling the `ValidateChanges` method of the DataForm.
* `LostFocus`&mdash;The changes are validates after the editor loses focus.
* `PropertyChanged`&mdash;The changes in the editor are validated immediately on each property change (when the property value changes).

The `ValidationMode` can be applied globally to the RadDataForm 

```XAML
<telerik:RadDataForm x:Name="dataForm"
                     ValidationMode="LostFocus"/>
```

or to each editor. 

```XAML
<telerik:RadDataForm x:Name="dataForm" AutoGenerateItems="False">
    <telerik:DataFormTextEntry PropertyName="FirstName" HeaderText="Name" ValidationMode="LostFocus"/>
    <telerik:DataFormNumericEditor PropertyName="People" HeaderText="People" Minimum="1" ValidationMode="PropertyChanged"/>
</telerik:RadDataForm>
```

## Methods

* `ValidateChanges`&mdash;Executes the validation logic associated with the DataForm control. This method is mostly useful when the `ValidationMode` is set to ``Explicit`.
The method returns `true` if the validation passes, otherwise `false`.

## Commands

* `ValidateCommand`(`ICommand`)&mdash;Gets a command to execute the validation logic of the RadDataForm. This command is mostly useful when the DataForm `ValidationMode` property is set to `Explicit`.

## Validation message - styling and customization

When validation is applied the DataForm has a default styles to the validation messaaged and validation summery messqage. In addition there is an image displayed. You can use the following properties for validation styling andcustomization:

* `ValidationSummaryImageSource`(`ImageSource`)&mdash;Specifies the `ImageSource` of the image displayed in the validation summary.
* `ValidationSummaryImageStyle`(`Style`)&mdash;Specifies the Style applied to the image of the validationsummary. The target type of this style is the .NET MAUI `Image` control.
* `ValidationSummaryStyle`(`Style`)&mdash;Specifies the style applied to the validation summary. The target type of this style is the `Telerik.Maui.Controls.DataFormValidationSummaryView`.         
* `ValidationSummaryLabelStyle`(`Style`)&mdash;Specifies the style applied to the labels of the validation summary. The target type of this style is the .NET MAUI `Label` control.
        

## See Also

