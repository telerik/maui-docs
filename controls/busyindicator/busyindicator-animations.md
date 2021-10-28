---
title: Animations
page_title: .NET MAUI BusyIndicator Documentation | Animations
description: Check our &quot;Animations&quot; documentation article for Telerik BusyIndicator for .NET MAUI.
position: 2
slug: busyindicator-animations
---

# Animations

The BusyIndicator provides options for controlling the behavior of its built-in animations and enables you to define custom animations.

## Built-in Animations

To change the selected animation of the BusyIndicator, use its `AnimationType` property. `AnimationType` is an enum that accepts values from `Animation1` to `Animation10`. By default, `AnimationType` is set to `Animation1`.

>important The animation will be displayed only when the `IsBusy` property is set to `True`.

![BusyIndicator animations list](images/busyindicator-features-animations-0.png)

## Controlling Size and Color

To change the size and color of the animated element (animation content), use the following properties:

* `AnimationContentWidthRequest` and `AnimationContentHeightRequest`&mdash;Define the animation size.
* `AnimationColor`&mdash;Customizes the color of the built-in animation.

>important `AnimationContentWidthRequest`, `AnimationContentHeightRequest`, and `AnimationColor` won't be applied if you use custom animations.

By default, the size of the animation content is 25x25 pixels.

The snippet below shows how to configure the predefined BusyIndicator animations.

<snippet id='busyindicator-animations-settings' />
```XAML
<telerikPrimitives:RadBusyIndicator x:Name="BusyIndicator"
									AnimationType="Animation2"
									AnimationContentColor="#2374FF"
									AnimationContentHeightRequest="150"
									AnimationContentWidthRequest="150"
									IsBusy="True">
    <telerikPrimitives:RadBusyIndicator.Content>
        <Label Text="This is displayed when the indicator is not busy."
               TextColor="Black" />
    </telerikPrimitives:RadBusyIndicator.Content>
</telerikPrimitives:RadBusyIndicator>
```

The image below shows the modified BusyIndicator in its busy state.

![BusyIndicator Settings](images/busyindicator-animations-settings.png)

## Custom Animations

To create a custom animation, use a combination of the `AnimationType`, `BusyContent`, and `Animations` properties:

1. To indicate to the control that you use a custom animation, set the `AnimationType` to `Custom`.

1. Add the content that you want to animate to `BusyContent`.

1. The custom animation is added to the `Animations` collection of the BusyIndicator.

The following example demonstrates how to create a custom animation that changes the opacity of a text (blinking effect) in XAML.

<snippet id='busyindicator-animations-xaml'/>
<snippet id='busyindicator-animations-code'/>
```XAML
<telerikPrimitives:RadBusyIndicator x:Name="radBusyIndicator"
									AnimationType="Custom"
									IsBusy="True">
    <telerikPrimitives:RadBusyIndicator.Content>
        <Label Text="This is the content of the RadBusyIndicator control displayed when the indicator is not busy." />
    </telerikPrimitives:RadBusyIndicator.Content>
    <telerikPrimitives:RadBusyIndicator.BusyContent>
        <Label HorizontalOptions="Center"
               Text="Loading..."
               VerticalOptions="Center" />
    </telerikPrimitives:RadBusyIndicator.BusyContent>
</telerikPrimitives:RadBusyIndicator>
```

The following example demonstrates how to create a custom animation that changes the opacity of a text (blinking effect) in code-behind.

<snippet id='busyindicator-animations-csharp'/>
```C#
RadBusyIndicator radBusyIndicator = new RadBusyIndicator()
{
    IsBusy = true,
    AnimationType = AnimationType.Custom,
    Content = new Label() { Text = "This is the content of the RadBusyIndicator control displayed when the indicator is not busy." },
    BusyContent = new Label()
    {
        Text = "Loading...",
        VerticalOptions = new LayoutOptions(LayoutAlignment.Center, false),
        HorizontalOptions = new LayoutOptions(LayoutAlignment.Center, false),
    },
};

RadDoubleAnimation annimation = new RadDoubleAnimation() { Duration = 800, From = 0.1, To = 1, PropertyPath = "Opacity", Target = radBusyIndicator.BusyContent, RepeatForever = true, AutoReverse = true };
radBusyIndicator.Animations.Add(annimation);

Device.StartTimer(TimeSpan.FromMilliseconds(5000),
    () =>
    {
        radBusyIndicator.IsBusy = false;
        return false;
    });
```

## See Also

- [Getting Started with the BusyIndicator]({% slug busyindicator-getting-started %})
