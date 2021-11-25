---
title: Events
page_title: .NET MAUI MaskedEntry Documentation | Events
description: Check our &quot;Events&quot; documentation article for Telerik MaskedEntry for .NET MAUI.
position: 7
slug: maskedentry-events
---

# Events

The MaskedEntry exposes the following events:

* `ValueChanging`: Occurs when the editing value is changing. Through the `MaskedEntryValueChangingEventArgs` you can get a hold of:

	* `NewValue`&mdash;Gets or sets the new Value to be set to the control.
	* `IsValid`&mdash;Gets or sets a value indicating the new value in considered valid according to internal (mask, regex) and external (application) validation.
	* `ValidationErrors`&mdash;Gets a list of the internal validation errors.
	* `ValidationMessage`&mdash;Gets or sets a validation message for the end user.
	* `Cancel`&mdash;Gets or sets a value indicating whether the event should be canceled.


* `ValueChanged`&mdash;Occurs when the editing value has been changed. This event is fired if the `ValueChanging` event is not canceled. Through the `MaskedEntryValueChangedEventArgs` you can get the following properties:

	* `Value`&mdash;Specifies the new value set to the control.
	* `Text`&mdash;Specifies the new value with the formatting applied.
	* `IsValid`&mdash;Indicates whether the new value is considered valid according to internal (mask, regex) and external (application) validation.
	* `ValidationMessage`&mdash;Defines a validation message for the end user.

## See Also

- [Getting Started]({%slug maskedentry-getting-started%})
