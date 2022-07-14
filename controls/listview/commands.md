---
title: Commands
page_title: .NET MAUI ListView Documentation - Commands
description: Review the Telerik UI for .NET MAUI ListView Commands for operations like item swiping, item tap, reordering, pull to refresh, grouping and more. 
position: 13
slug: listview-features-commands
previous_url: /controls/listview/listview-features-commands
tags: commands
---

# Commands

The Command design-pattern is widely used in the XAML and MVVM world. The ListView strictly follows the Command design-pattern best practices and provides an intuitive and easy-to-use set of APIs that allow you to control various aspects of ListView behavior.

The ListView exposes a `Commands` collection that allows you to register custom commands with each control’s instance through the `RadListView.Commands` property. `Commands` gets the collection with all the custom commands registered with the `CommandService`. Custom commands have higher priority than the built-in (default) ones.

## CommandId Enumeration

All predefined commands within a `RadListView` instance are identified by a member of the `CommandId` enumeration. This member is actually the key that relates a command instance to a particular action/routine within the owning ListView.

To register a custom command within a `RadListView` instance you can:

* [Inherit from the ListViewCommand class](#inheriting-from-listviewcommand) and override its `CanExecute` and `Execute` methods.
* [Use the ListViewUserCommand class and bind its Command property](#binding-listviewusercommand) to a `Command` in your `ViewModel`.

In both cases, you need to set the `Id` property of the new command so that it can be properly associated with the desired action/event.

Following are the members of the `CommandId` enumerations:

* `ItemTap`
* `ItemSwiping`
* `ItemSwipeCompleted`
* `ItemSwipeStarting`
* `PullToRefreshRequested`
* `SelectionChanged`
* `LoadOnDemand`
* `ItemHold`
* `GroupHeaderTap`
* `ReorderStarting`
* `ReorderEnded`

>tip These actions correspond to the events exposed by the ListView. For more details, see the [Events]({%slug listview-features-events%}) topic.

For each of the available commands, there is a `context` object of type `[CommandId]CommandContext`, for example, `ItemTapCommandContext`, `ItemHoldCommandContext`, and so on. The `context` object is passed as a parameter in its `Execute` method and provides information identical to the corresponding event arguments.

## Inheriting from ListViewCommand

To demonstrate inheriting from the `ListViewCommand`, the following example handles the `ItemTap` action as a Command:

1. Create a class that inherits from the `ListViewCommand` and set its `Id` property. Then override the `CanExecute` and `Execute` methods:

 <snippet id='listview-features-commands-listviewcommand'/>

1. Add the custom command to the Commands collection of the `RadListView` instance:

 <snippet id='listview-features-commands-add'/>

## Binding ListViewUserCommand

With the `ListViewUserCommand` binding approach, you can directly handle the custom commands in the `ViewModel`.

1. Add the custom command to the `ViewModel`:

 <snippet id='listview-features-commands-viewmodel'/>
 
1. Bind the `ItemTapCommand` through the predefined `ListViewUserCommand` command. Its `Id` property is used to map the command to the corresponding action with the control:

 <snippet id='listview-commands-listviewusercommand-xaml'/>

## See Also

- [Events]({%slug listview-features-events%})
- [Selection]({%slug listview-features-selection%})
- [Reordering]({%slug listview-features-reorder-items%})
