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

## See Also

