---
title: Overview
page_title: .NET MAUI DataForm Documentation - Grouping
description: Learn more about the grouping functionallity that Telerik UI for .NET MAUI DataForm control provides.
position: 0
slug: dataform-grouping
---

# .NET MAUI DataForm Grouping

Telerik UI for .NET MAUI DataForm supports grouping. You can define the groups directly in the DataForm or using the `GroupName` DisplayAttribute in the business model.

>important The `GroupName`(`string`) property is the identifier for each group.

### Define groups in XAML and add editors to the group

You can organize the Editors in groups using the `DataFormGroup`(`Telerik.Maui.controls.DataFormItem`). 

DataForm definition with Grouping applied:

<snippet id='dataform-grouping-from-XAML'/>

And the business model used:

<snippet id='dataform-editors-model'/>

### Use GroupName Display Attribute in the model

Apply grouping using the `GroupName` display attribute. More information about this can be found in the [Microsoft documentation](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute.groupname?view=net-6.0).

Example with `GroupName` display attribute applied in the business model. The model is used for RadDataForm:

<snippet id='dataform-grouping-model'/>

And the DataForm definition in XAML:

<snippet id='dataform-grouping-from-model'/>

### Define the groups in XAML and GroupName in the model

You can apply the groups in the XAML and set the `GroupName` property. Then inside the model add the `GroupName` attribute to the concrete property. 

DataForm XAML definition with grouping applied:

<snippet id='dataform-grouping-mix'/>

`GroupName` defined to the properties in the business model:

<snippet id='dataform-group-model'/>

## Events

Telerik .NET MAUI DataForm exposes event for group generation:

* `GroupGenerated`&mdash;Raised when the data form is about to generate a group of items automatically.
This event can be used to customize the automatic generation of groups in the data form, when the `Telerik.Maui.Controls.RadDataForm.AutoGenerateItems` property is `true` and there isn't no group specified explicitly for the given category in the `Telerik.Maui.Controls.RadDataForm.Items` collection. 
It's possible to customize, replace or discard the generated group, before is added to the dataform. The `GroupGenerated` event handler receives two parameters:
	* `sender` argument which is of type object, but can be cast to the `RadDataForm` type.
	* `DataFormGroupGeneratedEventArgs` which has a reference to the `GroupName`(`string`)&mdash;Gets the unique name of the group to generate, `Group`(`DataFormGroup`)&mdash;Specifies the group, which is generated for the specified unique name. To skip the generation of the group, set this property to null.


<snippet id='dataform-groupgenerated-event'/>

And the handler:

<snippet id='dataform-ongroups-generated'/>

> For CustomGenerate example refer to the DataForm/GettingStarted Category of the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}).

## See Also

- [Configure the Groups]({%slug dataform-grouping-configuration%})
