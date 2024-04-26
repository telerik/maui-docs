---
title: Configuration
page_title: .NET MAUI Expander Documentation - Configuration
description: Learn more about how to configure the Telerik UI for .NET MAUI Expander control.
position: 2
slug: expander-configuration
---

# .NET MAUI Expander Configuration

The purpose of this help article is to show you how to configure the Telerik .NET MAUI Expander control. 

## Collapsed/Expanded States

`RadExpander` provides an expandable container which can hold any content. You can show or hide this content by interacting with the `Header` of the control. The default state of `RadExpander` is collapsed.

You can use `IsExpanded` boolean property to switch the current state of the control.

## Expander Header

You can either apply `HeaderText` property or use the `ExpanderHeader` content control which provides a set of useful properties for customizing the way the header looks. For more details refer to [ExpanderHeader control]({% slug expander-header%}) topic.

<snippet id='expander-features-headerlocation'/>

This is the result:

![.NET MAUI Expander Header location](images/expander-header-location.png "Expander header location")

> For a runnable example with the Expander Header Location scenario, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **Expander > Features** category.

## Animation While Expanding or Collapsing

To enable or disable the animation you need to use the `IsAnimationEnabled` property of `RadExpander`. By default, the Animation is enabled.

You can also customize the duration and easing (acceleration over time) through `AnimationDuration`(in ms) and `AnimationEasing` (of type *Microsoft.Maui.Easing*) properties.

## See Also

- [Getting Started]({% slug expander-getting-started%})
