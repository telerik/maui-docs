---
title: Interaction
page_title: .NET MAUI SlideView Documentation - Infinite Looping
description: Learn about the infinite looping mechanism that SlideView control provides.
position: 7
slug: slideview-scrolling
---

# .NET MAUI SlideView Interaction

The users of the application can change the views by using the navigation buttons and pan gesture (on both mobile and desktop) and indicators (on desktop).

By default the pan gesture is disabled on desktop and enabled on mobile. You can change this behavior by using the `InteractionMode` (enum of type `Telerik.Maui.Controls.SlideView.SlideViewInteractionMode`) property. The available options are `None` (the default value on desktop) and `Pan` (the default value on mobile).

## Infinite Looping

By default, when you reach the last view, the **Next** button won't do anything. You can change this behavior through the `Has Looping` property and allow the repeating of the views when the user reaches the last view.

`HasLooping`(Default value`False`)&mdash;This property allows to achieve infinite looping.

See the result below in the `.gif` file:

![.NET MAUI SlideView Looping](images/slideview-overscroll.gif)

## See Also

- [Binding SlideView to Data]({%slug slideview-data-binding%})
- [Using Navigation Buttons in SlideView]({%slug slideview-interaction%})
- [Executing Commands on Slide Action]({%slug slideview-commands%})
- [Handling the SlideView Events]({%slug slideview-events%})
- [Using an Item Template in SlideView]({%slug slideview-item-template%})
- [Changing the SlideView Appearance through a Control Template]({%slug slideview-control-template%})
- [Styling the SlideView Component]({%slug slideview-navigation-buttons-styling%})
- [Styling the SlideView Indicators]({%slug indicators-styling%})
