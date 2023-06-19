---
title: Commit Data
page_title: .NET MAUI DataForm Documentation - Commit Data
description: "Commit the data using different options provided by the Telerik DataForm for .NET MAUI control."
position: 10
slug: dataform-commit-data
---

# .NET MAUI DataForm Commit Data

The values entered in the DataForm can be submitted to the underlying data object on three different occasions, using the `CommitMode` property of the DataForm.

![RadDataForm Overview](images/dataform-commit-data-desktop.png)

The next sections list all DataForm members related to commit data feature.

## Commit modes

The selected mode is applied through `CommitMode`(of type`Telerik.Maui.Controls.DataFormCommitMode`) property of the DataForm control. You could choose between three commit modes:

* `Explicit`&mdash;The changes are committed explicitly by invoking the `CommitCommand` or calling the `CommitChanges` method of the DataForm.
* `LostFocus`&mdash;The changes are committed after the editor loses focus.
* `PropertyChanged`&mdash;The changes in the editor are committed immediately on each property change (when the property value changes).

>important When `CommitMode` is set to `LostFocus`, you have to set `ValidatonMode` to `LostFocus` or `Explicit`.

The `CommitMode` can be applied globally to the RadDataForm 

```XAML
<telerik:RadDataForm x:Name="dataForm"
                     CommitMode="LostFocus"/>
```


## Properties

* `HasPendingChanges`(`bool`)&mdash;Gets a value indicating whether there are pending changes.

<snippet id='dataform-commit-mode'/>

## Manual Commit with Methods

**DataForm exposes a `CommitChanges` method with two overloads:**

* `CommitChanges()`&mdash;Commits all pending changes in the RadDataForm to the underlying business object. This method is mostly useful when the `CommitMode` is set to `Explicit`.
The method returns `true` if the validation passes, otherwise `false`.

<snippet id='dataform-commit-changes'/>

* `CommitChanges(string propertyName)`&mdash;Commit the pending changes in the editor for the specified property. This method is mostly useful when the DataForm `CommitMode` property is set to `Explicit`. `True` if the validation passes, `false` otherwise.

<snippet id='dataform-commit-changes-on-property'/>

**DataForm exposes a `CancleChanges` method with two overloads:**

* `CancelChanges`&mdash;Cancels all pending changes in the RadDataForm and reverts to the original values from the underlying business object. This method is mostly useful when the `CommitMode` property is set `Explicit`.

```C#
this.dataForm.CancelChanges();
```

* `CancelChanges(string propertyName)`&mdash;Cancels the pending changes in the editor for the specified property. This method is mostly useful when the DataForm `CommitMode` property is set to `Explicit`.

<snippet id='dataform-cancelchanges-on-property'/>

## Commands

* `CommitCommand`(`ICommand`)&mdash;Gets a command to a command to commit all pending changes in the RadDataForm. This command is mostly useful when the DataForm `CommitMode` property is set to `Explicit`.
* `CancelCommand`(`ICommand`)&mdash;Gets a command to cancel all pending changes in the RadDataForm. This command is mostly useful when the DataForm `CommitMode` property is set to `Explicit`.

>important All commit methods call validation first. If the property value passes validation, then the corresponding validation finished event is raised and the value is committed successfully.

## See Also

- [Editors]({%slug dataform-editors%})
- [Grouping]({%slug dataform-grouping%})
- [Headers]({%slug dataform-headers%})
- [Layouts]({%slug dataform-layouts%})
- [Commands]({%slug dataform-commands%})
