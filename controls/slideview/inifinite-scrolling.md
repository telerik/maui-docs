---
title: Infinite Scrolling
page_title: .NET MAUI SlideView Documentation - Infinite Scrolling
description: "Learn about the infinite scrolling mechanism that SlideView control provides."
position: 11
slug: slideview-scrolling
---

# .NET MAUI SlideView Infinite Scrollng

By default when you reach to the last view, the 'next' slide button won't do anything. You can alter this and allow repeating of the views when you reach the last view, via the `OverScrollMode` property.

* `OverScrollMode`&mdash;Defines the different behaviors of the SlideView control. In cases where it is not possible to move the items in the direction that the user is attempting. This can happen for the first and last items when the `HasLooping` property is set to false.

The property has two modes:

   * `None`&mdash;no overscroll will happen 
   * `Spring`&mdash;The end-user will be able to move the item in a direction that is otherwise not allowed, but the offset will be smaller than the pointer movement, thus creating a spring effect.

   

