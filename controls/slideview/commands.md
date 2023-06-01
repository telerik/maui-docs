---
title: Commands
page_title: .NET MAUI SlideView Documentation - Commands
description: Use the exposed commands of the Telerik UI for .NET MAUI SlideView to programmatically navigate throught the items.
position: 13
slug: slideview-commands
---

# .NET MAUI SlideView Commands

The Telerik UI for .NET MAUI SlideView provides a `Commands` collection with a number of commands that can be executed when the slide actions occurs.

The control provides commands that handle the navigation through the items:

* `NavigateToPreviousItemCommand` (`ICommand`)&mdash;Handles navigation to the previous item. If the RadSlideView `HasLooping` property is set to `true` and the current item is the first item, then the navigation to the last item will happen seemingly as if it was the previous item.

* `NavigateToNextItemCommand` (`ICommand`)&mdash;Handles the navigation to the next item. If the RadSlideView `HasLooping` property is set to true and the current item is the last item, then the navigation to the first item will happen seemingly as if it was the next item.

## Example 

The following example shows how to add a command.

**1.** Add the SlideView definition.

<snippet id='slideview-commands' />

## See Also

- [Binding SlideView to Data]({%slug slideview-data-binding%})
- [Using Navigation Buttons in SlideView]({%slug slideview-interaction%})
- [Handling the SlideView Events]({%slug slideview-events%})
- [Using an Item Template in SlideView]({%slug slideview-item-template%})
- [Changing the SlideView Appearance through a Control Template]({%slug slideview-control-template%})
- [Styling the SlideView Component]({%slug slideview-navigation-buttons-styling%})
- [Styling the SlideView Indicators]({%slug indicators-styling%})