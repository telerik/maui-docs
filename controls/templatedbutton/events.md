---
title: Events
page_title: .NET MAUI TemplatedButton Documentation - Events
description: Review TemplatedButton events that are raised when button is pressed, clicked, released and toggle state changes. 
position: 7
slug: templatedbutton-events
---

# .NET MAUI TemplatedButton Events

The .NET MAUI TemplatedButton emits a set of events that allow you to configure the component's behavior in response to specific user actions.

The .NET MAUI TemplatedButton exposes the following events:

* `Clicked`&mdash;Raised when the `RadTemplatedButton` is clicked. The `Clicked` event handler receives two parameters:
	* The `sender` argument, which is of type `RadTemplatedButton`.
	* A `EventArgs` object, which provides information on the `Clicked` event.

> For a runnable example demonstrating the TemplatedButton Clicked event, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **TemplatedButton > Events** category.

* `Pressed`&mdash;Raised when `RadTemplatedButton` is pressed. The `Pressed` event handler receives two parameters:
	* The `sender` argument, which is of type `RadTemplatedButton`.
	* An `EventHandler` object, which provides information on the `Pressed` event.

> For a runnable example demonstrating the TemplatedButton Pressed event, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **TemplatedButton > Events** category.
	
* `Released`&mdash;Raised when the `RadTemplatedButton` is released. The `Released` event handler receives two parameters:
	* The `sender` argument, which is of type `RadTemplatedButton`.
	* An `EventHandler` object, which provides information on the `Pressed` event.

> For a runnable example demonstrating the TemplatedButton Released event, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **TemplatedButton > Events** category.

## Using the Clicked Event

The following example demonstrates how to use the `Clicked` event:

**1.** Define the button in XAML:

<snippet id='templatedbutton-event-clicked' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Add the `Clicked` event:

<snippet id='templatedbutton-clicked-event' />

## Using the Pressed Event

The following example demonstrates how to use the `Pressed` event:

**1.** Define the button in XAML:

<snippet id='templatedbutton-event-pressed' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Add the `Pressed` event:

<snippet id='templatedbutton-pressed-event' />

## Using the Released Event

The following example demonstrates how to use the `Released` event:

**1.** Define the button in XAML:

<snippet id='templatedbutton-event-released' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Add the `Released` event:

<snippet id='templatedbutton-released-event' />

## See Also

- [Configure the TemplatedButton]({%slug templatedbutton-contenfiguration%})
- [Loading Button]({%slug templatedbutton-loading-button%})
- [Set Visual States]({%slug templatedbutton-visual-states%})
- [Execute Command]({%slug templatedbutton-command%})
- [Style the TemplatedButton]({%slug templatedbutton-styling%})