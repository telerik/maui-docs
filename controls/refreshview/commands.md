---
title: Commands
meta_title: .NET MAUI RefreshView Documentation - Commands
description: Learn how to execute a view model command when a refresh starts in the Telerik UI for .NET MAUI RefreshView and control when users can refresh.
components: ["refreshview"]
position: 12
slug: refreshview-commands
---

# .NET MAUI RefreshView Commands

The RefreshView executes a command when a refresh starts. Use the command to load data in your view model when you follow the Model-View-ViewModel (MVVM) pattern.

## Refresh Command Properties

The RefreshView exposes the following command properties:

* `Command` (`ICommand`)&mdash;Specifies the command that the RefreshView executes when a refresh starts. The command executes before the `Refreshing` event, if the command can execute.
* `CommandParameter` (`object`)&mdash;Specifies the parameter passed to the `Command`.

While the `CanExecute` method of the command returns `false`, pull gestures don't start a refresh. Setting `IsRefreshing` to `true` still starts a refresh.

## Execute a Command on Refresh

The following example demonstrates how to bind the `Command`, `CommandParameter`, and `IsRefreshing` properties of the RefreshView to a view model.

1. Define the RefreshView in XAML:

    <snippet id='refreshview-commands' />

2. Add the `telerik` namespace:

    ```XAML
    xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
    ```

3. Define the command in your view model. When the data is loaded, set `IsRefreshing` to `false` to end the refresh:

    <snippet id='refreshview-commands-viewmodel' />

> tip For a runnable example demonstrating the RefreshView commands, see the [SDKBrowser Demo Application]({% slug sdkbrowser-app %}) and go to the **RefreshView > Commands** category.

## See Also

- [RefreshView Events]({% slug refreshview-events %})
- [Refresh State]({% slug refreshview-refresh-state %})
- [RefreshView Integration with CollectionView]({% slug refreshview-collectionview %})
- [RefreshView Integration with DataGrid]({% slug refreshview-datagrid %})
