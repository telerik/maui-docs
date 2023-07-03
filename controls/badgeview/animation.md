---
title: Animation
page_title: .NET MAUI BadgeView Documentation - Animation
description: Try now the Telerik UI for .NET MAUI BadgeView that allows you to display the Badge indicator with an animation flow
tags: badge, animation, badgeview for .net maui, badge for .net maui
position: 7
slug: badgeview-animation
---

# .NET MAUI BadgeView Animation

The `BadgeView` allows you to display the Badge indicator with an animation flow.

The following properties are related to the Badge animation feature:

* `BadgeAnimationType`(enum of type `Telerik.Maui.Controls.Compatibility.Primitives.BadgeAnimationType`)&mdash;Specifies the type of the animation applied to the BadgeView. You can choose between two options: `None` and `Scale`. The default `BadgeAnimationType` is `Scale`.

* `BadgeAnimationDuration`(`int`)&mdash;Specifies the duration for the Badge animation in milliseconds. The default value is `300`.

* `BadgeAnimationEasing`(`Microsoft.Maui.Easing`)&mdash;Specifies the easing of the badge animation. The default value is `SinInOut`.

* `BadgeStartAnimationCommand`(`System.Windows.Input.ICommand`)&mdash;Gets the command that starts the Badge animation.

```C#
this.badgeView.BadgeStartAnimationCommand.Execute(null);
```

## Example

The following example demonstrates how to set the `Animation` properties to the BadgeView:

<snippet id='badgeview-animation'/>

>tip For the Badge Animation example, go to the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and navigate to BadgeView -> Features category.

## See Also

- [Predefined Badges]({%slug badgeview-predefined-badges%})
- [Badge Position and Alignment]({%slug badgeview-position-alignment%})
