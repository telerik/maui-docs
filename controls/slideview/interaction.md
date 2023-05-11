---
title: Interaction
page_title: .NET MAUI SlideView Documentation - Interaction
description: "Learn how to interact with the navigation buttons of the SlideView control."
position: 10
slug: slideview-interaction
---

# .NET MAUI SlideView Interaction

When you slide the tgriught the difeerent views you van use `Navigation Buttons`.
the SlideView exposes a `NavigationButtonVisibility` property which defines different visibility options:

 * `Visisble`&mdash;defines when the buttons are visible

 * `HiddenWhenDisabled`&mdash;defines when the buttons are visible when enabled, and hidden when disabled.

  * `Collapsed`&mdash;defines when the button is not visible 

When you slide throught the different view of the control with the Navigation Buttons, the SlideView exposes these commands:

* `NavigateToPreviousItemCommand`(`ICommand`)&mdash;Get a command that handles navigation to the previous item. If the RadSlideView `HasLooping` property is set to true and the current item is the first item, then navigation to the last item can happen and will happen seemingly as if it was the previous item.

* `NavigateToNextItemCommand` (`ICommand`)&mdash;Get a command that handles the navigation to the next item. If the RadSlideView `HasLooping` property is set to true and the current item is the last item, then navigation to the first item can happen and will happen seemingly as if it was the next item.


