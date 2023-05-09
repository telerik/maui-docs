---
title: Commands
page_title: .NET MAUI SlideView Documentation - Commands
description: Check our &quot;Commands&quot; documentation article for Telerik UI for .NET Maui SlideView control.
position: 4
slug: slideview-commands
---

# .NET MAUI SlideView Commands

The Telerik UI for .NET MAUI SlideView exposes a number of commands which will be executed when the slide actions occurs. To do this you can use the **Commands** collection.

The control provides commands that handles the navigations throught the items:

* `NavigateToPreviousItemCommand`(`ICommand`)&mdash;Get a command that handles navigation to the previous item. If the RadSlideView `HasLooping` property is set to true and the current item is the first item, then navigation to the last item can happen and will happen seemingly as if it was the previous item.

* `NavigateToNextItemCommand` (`ICommand`)&mdash;Get a command that handles the navigation to the next item. If the RadSlideView `HasLooping` property is set to true and the current item is the last item, then navigation to the first item can happen and will happen seemingly as if it was the next item.

## Example 

This example shows how to add a command.

First, add the SlideView definition:

<snippet id='slideview-commands' />

And then, the commands which in this example are bind to buttons:

<snippet id='slideview-commands-button' />

<snippet id='slideview-commands-button-clicked' />