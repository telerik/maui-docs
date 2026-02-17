---
title: Animations
page_title: .NET MAUI BusyIndicator Documentation - Animations
description: Learn how to controll the size and color of built-in animations and how to define custom animations in Telerik UI Busy Indicator .NET MAUI control.
position: 2
previous_url: /controls/busyindicator/busyindicator-animations
slug: busyindicator-animations
---

# Animations in .NET MAUI BusyIndicator

The BusyIndicator provides options for controlling the size and color of its built-in animations and enables you to define custom animations.

## Built-in Animations

To change the selected animation of the BusyIndicator, use its `AnimationType` property. `AnimationType` is an enum that accepts values from `Animation1` to `Animation10`. By default, `AnimationType` is `Animation1`.

>important The animation will be displayed only when the `IsBusy` property is `True`.

![BusyIndicator animations list](images/busyindicator-features-animations-0.png)

### Controlling Size and Color

To change the size and color of the animated element (animation content), use the following properties:

* `AnimationContentWidthRequest` and `AnimationContentHeightRequest`&mdash;Define the animation size.
* `AnimationContentColor`&mdash;Customizes the color of the built-in animation.

>important `AnimationContentWidthRequest`, `AnimationContentHeightRequest`, and `AnimationContentColor` won't be applied if you use custom animations.

By default, the size of the animation content is `25x25` pixels.

The snippet below shows how to configure the predefined BusyIndicator animations.

<snippet id='busyindicator-animations-settings' />

The image below shows the modified BusyIndicator in its busy state.

![BusyIndicator Settings](images/busyindicator-animations-settings.png)

## Custom Animation

To create a custom animation, use a combination of the `AnimationType`, `BusyContent`, and `Animations` properties:

1. To indicate to the control that you use a custom animation, set the `AnimationType` to `Custom`.

1. Add the content that you want to animate to `BusyContent`.

1. The custom animation is added to the `Animations` collection of the BusyIndicator.

The `Animations`(Collection of type `RadAnimation`)&mdash;Used when the `AnimationType` of the BusyIndicator control is `Custom`.

The following example demonstrates how to create a custom animation that changes the opacity of a text (blinking effect) in XAML and in C#.

<snippet id='busyindicator-animations-xaml'/>
<snippet id='busyindicator-animations-code'/>

## See Also

- [Custom Busy Content]({% slug busyindicator-custom-busy-content%})
- [Adding an Image Inside the BusyIndicator for .NET MAUI]({%slug add-image-inside-busyindicator-dotnet-maui%})