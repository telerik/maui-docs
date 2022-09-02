---
title: Overview
page_title: .NET MAUI DataForm Documentation | Grouping
description: Check our &quot;Grouping&quot; documentation article for Telerik DataForm for .NET MAUI control.
position: 0
slug: dataform-grouping
---

# Grouping

Telerik UI for .NET MAUI DataForm supports grouping. You can define the groups directly in the DataForm or using the `GroupName` DisplayAttribute in the business model.

>important The `GroupName`(`string`) property is the identifier for each group.

### Define groups in XAML and add editors to the group

You can easily organize the Editors in groups using the `DataFormGroup`(`Telerik.Maui.controls.DataFormItem`). 

DataForm definition with Grouping applied:

<snippet id='dataform-grouping-from-XAML'/>

And the business model used:

<snippet id='dataform-editors-model'/>

### Use GroupName Display Attribute in the model

Apply goruping using the `GroupName` display attribute. More information about this can be found in the [Microsoft documentation](https://docs.microsoft.com/en-us/dotnet/api/system.componentmodel.dataannotations.displayattribute.groupname?view=net-6.0).

Example with `GroupName` display attribute applied in the business model. The model is used for RadDataForm:

<snippet id='dataform-grouping-model'/>

And the DataForm definition in XAML:

<snippet id='dataform-grouping-from-model'/>

### Define the groups in XAML and GroupName in the model

You acan apply the groups in the XAML and set the `GroupName` property. Then inside the model add the GroupName attribute to the concrete proeprty. 

DataForm XAML definition with goruping applied:

<snippet id='dataform-grouping-mix'/>

`GroupName` defined to the properties in the business model:

<snippet id='dataform-group-model'/>

## See Also
