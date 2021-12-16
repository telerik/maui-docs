---
title: Events
page_title: .NET MAUI MaskedEntry Documentation | Events
description: Check our &quot;Events&quot; documentation article for Telerik MaskedEntry for .NET MAUI.
position: 10
slug: maskedentry-events
---

# Events

The MaskedEntry exposes a set of events.

* `ValueChanging`&mdash;Occurs when the editing value is changing. Through the `MaskedEntryValueChangingEventArgs` you can set the following properties:

	* `NewValue`&mdash;Gets or sets the new value that will be set to the control.
	* `IsValid`&mdash;Gets or sets a value indicating whether the new value is considered valid according to internal (mask, regex) and external (application) validation.
	* `ValidationErrors`&mdash;Gets a list of the internal validation errors.
	* `ValidationMessage`&mdash;Gets or sets a validation message for the end user.
	* `Cancel`&mdash;Gets or sets a value indicating whether the event will be canceled.

* `ValueChanged`&mdash;Occurs when the editing value has been changed. `ValueChanged` is fired if the `ValueChanging` event is not canceled. Through the `MaskedEntryValueChangedEventArgs` you can set the following properties:

	* `Value`&mdash;Specifies the new value set to the control.
	* `Text`&mdash;Specifies the new value with the formatting applied.
	* `IsValid`&mdash;Indicates whether the new value is considered valid according to internal (mask, regex) and external (application) validation.
	* `ValidationMessage`&mdash;Defines a validation message for the end user.

>tip For the **Events** example, refer to the **MaskedEntry/Events** folder of the [SDK .NET MAUI Application]({%slug maui-demo-app%}).

## See Also

- [Getting Started]({%slug maskedentry-getting-started%})
- [Mask Types]({%slug maskedentry-masked-types%})
- [Validation]({%slug maskedentry-validation%})
- [Null Values Support]({%slug maskedentry-value%}#null-value-support})
- [Globalization]({%slug maskedentry-globalization%})
