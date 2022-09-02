---
title: Commit Data
page_title: .NET MAUI DataForm Documentation | Commit Data
description: Commit the data using different options provided by the Telerik DataForm for .NET MAUI control.
position: 10
slug: dataform-commit-data
---

# Commit Data

The values entered in the DataForm can be submitted to the underlying data object on three different occasions, using the `CommitMode` property of the DataForm.

The next sections list all DataForm members related to commit data feature.

## Commit modes

The selected mode is applied through `CommitMode`(of type`Telerik.Maui.Controls.DataFormCommitMode`) property of the DataForm control. You could choose between three commit modes:

* `Explicit`&mdash;The changes are committed explicitly by invoking the `CommitCommand` or calling the `CommitChanges` method of the DataForm.
* `LostFocus`&mdash;The changes are committed after the editor loses focus.
* `PropertyChanged`&mdash;The changes in the editor are committed immediately on each property change (when the property value changes).

The `CommitMode` can be applied globally to the RadDataForm 

```XAML
<telerik:RadDataForm x:Name="dataForm"
                     CommitMode="LostFocus"/>
```

or to each editor. 

```XAML
<telerik:RadDataForm x:Name="dataForm" AutoGenerateItems="False">
    <telerik:DataFormTextEntry PropertyName="FirstName" HeaderText="Name" CommitMode="LostFocus"/>
    <telerik:DataFormNumericEditor PropertyName="People" HeaderText="People" Minimum="1" CommitMode="PropertyChanged"/>
</telerik:RadDataForm>
```

## Methods

* `CommitChanges`&mdash; Commits all pending changes in the RadDataForm to the underlying business object. This method is mostly useful when the `CommitMode` is set to ``Explicit`.
The method returns `true` if the validation passes, otherwise `false`.

* `CancelChnages`&mdash;Cancels all pending changes in the RadDataForm and reverts to the original values from the underlying business object. This method is mostly useful when the `CommitMode` property is set `Explicit`.

## Commands

* `CommitCommand`(`ICommand`)&mdash;Gets a command to a command to commit all pending changes in the RadDataForm. This command is mostly useful when the DataForm `CommitMode` property is set to `Explicit`.

>important All commit methods call validation first. If the property value passes validation, then the corresponding validation finished event is raised and the value is committed successfully.

## See Also