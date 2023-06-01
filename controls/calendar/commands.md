---
title: Commands
page_title: .NET MAUI Calendar Documentation - Commands
description: "Review all available commands for navigation to upper - lower view and next - previous month, year, century, decade that Calendar for .NET MAUI provides."
position: 12
slug: calendar-commands
---

# .NET MAUI Calendar Commands

This article explains all command Calendar control provides.

## Commands for navigating the current view

The following commands are related to the navigation between the current view:

* `NavigateToNextViewCommand`(`ICommand`)&mdash;Gets the command that is executed when the user navigates to the next view..
* `NavigateToPreviousViewCommand`(`ICommand`)&mdash;Gets the command that is executed when the user navigates to the previous view.

## Commands for navigating between views

The following commands are related to the navigation between the views: 

* `NavigateToUpperViewCommand`(`ICommand`)&mdash;Gets the command that is executed when the user navigates to the upper view.
* `NavigateToLowerViewCommand`(`ICommand`)&mdash;Gets the command that is executed when the user navigates to the lower view..

The navigation flow for upper view is as follow&mdash;Month -> Year -> Decade -> Century.
The navigation flow for lower view is as follow&mdash;Century -> Decade -> Year -> Month.

## Example

Calendar definition:

<snippet id='calendar-navigation-commands'/>

The `NavigateToNextViewCommand` and `NavigateToPreviousViewCommand` execution on button click:

<snippet id='calendar-navigating-in-current-view'/>

The `NavigateToUpperViewCommand` and `NavigateToLowerViewCommand` execution on button click:

<snippet id='calendar-navigating-detween-views'/>

> For the Calendar Commands example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to Calendar -> Commands category.

## See Also
