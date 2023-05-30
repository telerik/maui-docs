---
title: Navigation Buttons
page_title: .NET MAUI SlideView Documentation - Navigation Buttons
description: Learn how to interact with the navigation buttons of the SlideView control.
position: 10
slug: slideview-interaction
---

# .NET MAUI SlideView Navigation Buttons

To switch through the different views of the SlideView, you van use Navigation Buttons.

The SlideView exposes a `NavigationButtonVisibility` property that allows you to control the visibility options of the Navigation Buttons:

* `Visisble`&mdash;The buttons are visible.

* `HiddenWhenDisabled`&mdash;The buttons are visible when enabled and hidden when disabled.

* `Collapsed`&mdash;The buttons are not visible.

When you slide through the different views with the Navigation Buttons, the SlideView exposes the following commands:

* `NavigateToPreviousItemCommand` (`ICommand`)&mdash;Handles navigation to the previous item. If the RadSlideView `HasLooping` property is set to `true` and the current item is the first item, then the navigation to the last item will happen seemingly as if it was the previous item.

* `NavigateToNextItemCommand` (`ICommand`)&mdash;Handles the navigation to the next item. If the RadSlideView `HasLooping` property is set to true and the current item is the last item, then the navigation to the first item will happen seemingly as if it was the next item.
