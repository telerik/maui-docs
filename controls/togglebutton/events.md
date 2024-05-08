---
title: Events
page_title: .NET MAUI ToggleButton Documentation - Events
description: Review ToggleButton events that are raised when button is pressed, clicked, released and toggle state changes. 
position: 7
slug: togglebutton-events
---

# .NET MAUI ToggleButton Events

The .NET MAUI ToggleButton emits a set of events that allow you to configure the component's behavior in response to specific user actions.

The .NET MAUI ToggleButton exposes the following events:

* `IsToggledChanged`&mdash;Occurs when the `RadToggleButton.IsToggled` property is changed. The `IsToggledChanged` event handler receives two parameters:
    * The `sender` which is of type `Telerik.Maui.Controls.RadToggleButton`.
    * and `ValueChangedEventArgs`. The `ValueChangedEventArgs` provides the following properties:
        * `NewValue`(`TValue`)&mdash;Gets the new value from the `IsToggled` property.
        * `PreviousValue`(`TValue`)&mdash;Gets the previous value of the `IsToggled` property.

> For a runnable example demonstrating the ToggleButton IsToggledChanged event, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **ToggleButton > Events** category.

* `Clicked`&mdash;Raised when the `RadToggleButton` is clicked. The `Clicked` event handler receives two parameters:
	* The `sender` argument, which is of type `RadToggleButton`.
	* A `EventArgs` object, which provides information on the `Clicked` event.

> For a runnable example demonstrating the ToggleButton Clicked event, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **ToggleButton > Events** category.

* `Pressed`&mdash;Raised when `RadToggleButton` is pressed. The `Pressed` event handler receives two parameters:
	* The `sender` argument, which is of type `RadToggleButton`.
	* An `EventHandler` object, which provides information on the `Pressed` event.

> For a runnable example demonstrating the ToggleButton Pressed event, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **ToggleButton > Events** category.
	
* `Released`&mdash;Raised when the `RadToggleButton` is released. The `Released` event handler receives two parameters:
	* The `sender` argument, which is of type `RadToggleButton`.
	* An `EventHandler` object, which provides information on the `Pressed` event.

> For a runnable example demonstrating the ToggleButton Released event, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **ToggleButton > Events** category.

## Using the IsToggledChanged Event

The following example demonstrates how to use the `IsToggledChanged` event:

**1.** Define the button in XAML:

<snippet id='togglebutton-events-togglechanged' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Add the `IsToggledChanged` event:

<snippet id='togglebutton-events-togglechanged-handler' />

## Using the Clicked Event

The following example demonstrates how to use the `Clicked` event:

**1.** Define the button in XAML:

<snippet id='togglebutton-event-clicked' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Add the `Clicked` event:

<snippet id='togglebutton-clicked-event' />

## Using the Pressed Event

The following example demonstrates how to use the `Pressed` event:

**1.** Define the button in XAML:

<snippet id='togglebutton-event-pressed' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Add the `Pressed` event:

<snippet id='togglebutton-pressed-event' />

## Using the Released Event

The following example demonstrates how to use the `Released` event:

**1.** Define the button in XAML:

<snippet id='togglebutton-event-released' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Add the `Released` event:

<snippet id='togglebutton-released-event' />

## See Also

- [Configure the ToggleButton]({%slug togglebutton-contenfiguration%})
- [Toggle State]({%slug togglebutton-toggle-states%})
- [Apply Ripple Effect]({%slug togglebutton-ripple%})
- [Set Visual States]({%slug togglebutton-visual-states%})
- [Execute Command]({%slug togglebutton-command%})
- [Style the ToggleButon]({%slug togglebutton-styling%})