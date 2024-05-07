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

* `Clicked`&mdash;Raised when the `RadToggleButton` is clicked. The `Clicked` event handler receives two parameters:
	* The `sender` argument, which is of type `RadToggleButton`.
	* A `EventArgs` object, which provides information on the `Clicked` event.

* `Pressed`&mdash;Raised when `RadToggleButton` is pressed. The `Pressed` event handler receives two parameters:
	* The `sender` argument, which is of type `RadToggleButton`.
	* An `EventHandler` object, which provides information on the `Pressed` event.
	
* `Released`&mdash;Raised when the `RadToggleButton` is released. The `Released` event handler receives two parameters:
	* The `sender` argument, which is of type `RadToggleButton`.
	* An `EventHandler` object, which provides information on the `Pressed` event.


> For a runnable example demonstrating the ToggleButton events, see the [SDKBrowser Demo Application]({%slug sdkbrowser-app%}) and go to **ToggleButton > Events** category.

## See Also

