---
title: Events
page_title: .NET MAUI TemplatedButton Documentation - Events
description: Review TemplatedButton events that are raised when button is pressed, clicked, and released. 
position: 7
slug: templatedbutton-events
---

# .NET MAUI TemplatedButton Events

The .NET MAUI TemplatedButton emits a set of events that allow you to configure the component's behavior in response to specific user actions.

The .NET MAUI TemplatedButton exposes the following events:

* `Clicked`&mdash;Raised when the `RadTemplatedButton` is clicked or tapped. The `Clicked` event handler receives two parameters:
	* The `sender` argument which is of type `RadTemplatedButton`.
	* An `EventArgs` object which provides information on the `Clicked` event.

* `Pressed`&mdash;Raised when `RadTemplatedButton` is pressed (a finger presses on the buton, or a mouse button is pressed with a pointer positioned over the button). The `Pressed` event handler receives two parameters:
	* The `sender` argument which is of type `RadTemplatedButton`.
	* An `EventHandler` object which provides information about the `Pressed` event.

* `Released`&mdash;Raised when the `RadTemplatedButton` is released (the finger or mouse button is released). The `Released` event handler receives two parameters:
	* The `sender` argument which is of type `RadTemplatedButton`.
	* An `EventHandler` object which provides information on the `Released` event.

## Using the Clicked Event

The following example demonstrates how to use the `Clicked` event.

**1.** Define the button in XAML:

<snippet id='templatedbutton-event-clicked' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Add the `Clicked` event:

<snippet id='templatedbutton-clicked-event' />

This is the result on WinUI:

![.NET MAUI TemplatedButton Clicked Event](images/templatedbutton-clicked-event.gif "TemplatedButton for .NET MAUI")

> For a runnable example demonstrating the TemplatedButton Clicked event, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **TemplatedButton > Events** category.

## Using the Pressed Event

The following example demonstrates how to use the `Pressed` event.

**1.** Define the button in XAML:

<snippet id='templatedbutton-event-pressed' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Add the `Pressed` event:

<snippet id='templatedbutton-pressed-event' />

This is the result on WinUI:

![.NET MAUI TemplatedButton Pressed Event](images/templatedbutton-pressed-event.gif "TemplatedButton for .NET MAUI")

> For a runnable example demonstrating the TemplatedButton Pressed event, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **TemplatedButton > Events** category.

## Using the Released Event

The following example demonstrates how to use the `Released` event.

**1.** Define the button in XAML:

<snippet id='templatedbutton-event-released' />

**2.** Add the `telerik` namespace:

```XAML
xmlns:telerik="http://schemas.telerik.com/2022/xaml/maui"
```

**3.** Add the `Released` event:

<snippet id='templatedbutton-released-event' />

This is the result on WinUI:

![.NET MAUI TemplatedButton Released Event](images/templatedbutton-released-event.gif "TemplatedButton for .NET MAUI")

> For a runnable example demonstrating the TemplatedButton Released event, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to the **TemplatedButton > Events** category.

## See Also

- [Configure the TemplatedButton]({%slug templatedbutton-configuration%})
- [Loading Button]({%slug templatedbutton-loading-button%})
- [Set Visual States]({%slug templatedbutton-visual-states%})
- [Execute Command]({%slug templatedbutton-command%})
- [Style the TemplatedButton]({%slug templatedbutton-styling%})