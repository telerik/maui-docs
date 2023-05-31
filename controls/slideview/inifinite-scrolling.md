---
title: Infinite Scrolling
page_title: .NET MAUI SlideView Documentation - Infinite Scrolling
description: Learn about the infinite scrolling mechanism that SlideView control provides.
position: 11
slug: slideview-scrolling
---

# .NET MAUI SlideView Infinite Scrolling

By default, when you reach the last view, the **Next** slide button won't do anything. You can change this behavior through the `OverScrollMode` property and allow repeating of the views when the user reaches the last view.

The `OverScrollMode` property defines the possible behavior of the SlideView control in cases where the items cannot move in the direction selected by the user. This can happen for the first and last items when you set the `HasLooping` property to `false`.

The `OverScrollMode` property has two modes:

* `None`&mdash;No overscroll will happen.
* `Spring`&mdash;The end-user will be able to move an item in a direction that is otherwise not allowed, but the offset will be smaller than the pointer movement, thus creating a spring effect.  

   
