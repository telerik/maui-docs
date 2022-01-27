---
title: Badge Animation
page_title: .NET MAUI BadgeView Documentation | RadBadgeView Animation
description: "Check our &quot;Badge Animation&quot; documentation article for Telerik BadgeView for .NET MAUI."
tags: badge, animation, badgeview for .net maui, badge for .net maui
position: 4
slug: badgeview-animation
---

# Badge Animation

BadgeView allows you to display the badge indicator using animation. The following properties are related to the Badge animation feature:

* `BadgeAnimationType`(enum of type `Telerik.XamarinForms.Primitives.BadgeAnimationType`): Specifies the type of the animation applied to the BadgeView. You can choose between two options: `None` and `Scale`. The default BadgeAnimationType is `Scale`. 

* `BadgeAnimationDuration`(`int`): Specifies the duration for the badge animation in milliseconds. The default value is `300`.

* `BadgeAnimationEasing`(`Microsoft.Maui.Easing`): Specifies the Easing of the badge animation. The default value is `SinInOut`.

* `BadgeStartAnimationCommand`(`System.Windows.Input.ICommand`): Gets the command that starts the badge animation.

```C#
this.badgeView.BadgeStartAnimationCommand.Execute(null);
```

## Example

Here is the Animation properties set to the RadBadgeVierw control:

<snippet id='badgeview-animation'/>

>tip Badge Animation example can be found in [SDKBrowser Demo Application]({%slug maui-demo-app%}), just navigate to BadgeView -> Features category.

## See Also

- [Predefined Badges]({%slug badgeview-predefined-badges%})
- [Badge Position and Alignment]({%slug badgeview-position-alignment%})