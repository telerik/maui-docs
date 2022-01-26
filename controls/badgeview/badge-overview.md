---
title: Badge Control
page_title: .NET MAUI Badge Documentation | Badge Overview
description: Check our &quot;Badge&quot; documentation article for Telerik Badge for .NET MAUI.
position: 12
slug: badge-overview
---

# Badge Control

This article explains the `RadBadge` conrol and it's features. Also what is the difference between the `RadBadge` and `RadBadgeView` controls

## Badge vs BadgeView 

![Badge vs BadgeView](images/badge-badgeview.png)

Badge is the marker which is displayed to show notifications, statuses, etc. The BadgeView is the control in which you can add a content and position the badge based on this content. 

>important We recommend you use the [BadgeView control]({%slug badgeview-overview%})

## Define the Badge 

Here is the XAML definition of the `RadBadge`:

```XAML
<telerikPrimitives:Badge/>
```

And the namespace used:

```XAML
xmlns:telerikPrimitives="clr-namespace:Telerik.XamarinForms.Primitives;assembly=Telerik.Maui.Controls.Compatibility"
```

## Features 

Badge has the following properties: 

* `Text`(`string`): Defines the badge text.
* `TextColor`(`Microsoft.Maui.Graphics.Color`): Defines the text color of the badge.
* `TextMargin`(`Microsoft.Maui.Thickness`): Defines the margin of the badge text.
* `FontSize`(`double`): Defines the badge text font size.
* `FontFamily`(`string`): Defines the badge text font family.
* `FontAttributes`(`Microsoft.Maui.Controls.FontAttributes`): Defines the badge text font attributes.
* `BorderColor`(`Microsoft.Maui.Graphics.Color`): Defines the badge border color.
* `CornerRadius`(`Microsoft.Maui.Thickness`): Defines the corner radius of the badge border.
* `BorderThickness`(`Microsoft.Maui.Thickness`): Defines the badge border thickness.
* `AnimationType`(`Telerik.XamarinForms.Primitives.BadgeAnimationType`). You can choose between `Scale` and `None`. The default value is `Scale`.
* `AnimationEasing`(`Microsoft.Maui.Easing`): Defines the animation easing. For more details about different easing options check the [Xamarin.Forms.Easing](https://docs.microsoft.com/en-us/xamarin/xamarin-forms/user-interface/animation/easing) article. The default value is `SinInOut`.
* `AnimationDuration` in milliseconds(`int`) Defines the animation duration in milliseconds. The default value is 300.
* `ControlTemplate`(`Microsoft.Maui.Controls.ControlTemplate`): Specifies the Badge control template.

## Default ControlTemplate

The default Badge ControlTemplate definition in XAML

<snippet id='badgeview-badge-control-template'/>

Define the Badge:

```XAML
<telerikPrimitives:Badge/>
```

Add the following namespace:

```XAML
xmlns:telerikPrimitives="clr-namespace:Telerik.XamarinForms.Primitives;assembly=Telerik.Maui.Controls.Compatibility"
```

## See Also

- [BadgeView Overview]({%slug badgeview-overview%})
- [BadgeView Getting Started]({%slug badgeview-getting-started%})
- [Badge Position and Alignment]({%slug badgeview-position-alignment%})
- [Badge Animation]({%slug badgeview-animation%})
- [Badge Types]({%slug badgeview-predefined-badges%})
- [Badge Styling]({%slug badgeview-styling%})
- [Badge Customization]({%slug badgeview-customization%})