---
title: Events
page_title: .NET MAUI MaskedEntry Documentation | Events
description: Check our &quot;Events&quot; documentation article for Telerik MaskedEntry for .NET MAUI.
position: 7
slug: maskedentry-events
---

# Events

RadMaskedEntry exposes the following events:

* `ValueChanging`: Occurs when the editing value is changing. Through the `MaskedEntryValueChangingEventArgs` you can get a hold of:

	* NewValue: Gets or sets the new Value to be set to the control.
	* IsValid: Gets or sets a value indicating the new value in considered valid according to internal (mask, regex) and external (application) validation.
	* ValidationErrors: Gets a list of the internal validation errors.
	* ValidationMessage: Gets or sets a validation message for the end user.
	* Cancel: Gets or sets a value indicating whether the event should be canceled.
	
	
* `ValueChanged`: Occurs when the editing value has been changed. This event is fired if the `ValueChanging` event is not canceled. Through the `MaskedEntryValueChangedEventArgs` you can get the following properties:

	* Value: Specifies the new value set to the control;
	* Text: Specifies the new value with the formatting applied;
	* IsValid: Indicates whether the new value is considered valid according to internal (mask, regex) and external (application) validation.
	* ValidationMessage: Defines a validation message for the end user.

## See Also

- [Getting Started]({%slug maskedentry-getting-started%})