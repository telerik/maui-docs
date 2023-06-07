---
title: Infinite Looping
page_title: .NET MAUI SlideView Documentation - Infinite Looping
description: Learn about the infinite looping mechanism that SlideView control provides.
position: 7
slug: slideview-scrolling
---

# .NET MAUI SlideView Infinite Looping

By default, when you reach the last view, the **Next** slide button won't do anything. You can change this behavior through the `OverScrollMode` property and allow repeating of the views when the user reaches the last view.

The `OverScrollMode` property defines the possible behavior of the SlideView control in cases where the items cannot move in the direction selected by the user.

The `OverScrollMode` property has two modes:

* `None`&mdash;No overscroll will happen.
* `Spring`(Default)&mdash;The end-user will be able to move an item in a direction that is otherwise not allowed, but the offset will be smaller than the pointer movement, thus creating a spring effect.

`HasLooping`(Default value`False`)&mdash;this property allows to achieve infinite looping.

See the result below in the .gif file:

![SlideView OverScroll](images/slideview-overscroll.gif)

## See Also

- [Binding SlideView to Data]({%slug slideview-data-binding%})
- [Using Navigation Buttons in SlideView]({%slug slideview-interaction%})
- [Executing Commands on Slide Action]({%slug slideview-commands%})
- [Handling the SlideView Events]({%slug slideview-events%})
- [Using an Item Template in SlideView]({%slug slideview-item-template%})
- [Changing the SlideView Appearance through a Control Template]({%slug slideview-control-template%})
- [Styling the SlideView Component]({%slug slideview-navigation-buttons-styling%})
- [Styling the SlideView Indicators]({%slug indicators-styling%})