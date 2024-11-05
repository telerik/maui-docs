---
title: Events
page_title: .NET MAUI NumericInput Documentation - Events
description: Learn more about the events that the Telerik UI for .NET MAUI NumericInput control provides.
position: 8
previous_url: /controls/numericinput/numericinput-events
slug: numericinput-events
---

# .NET MAUI NumericInput Events

The NumericInput exposes a `ValueChanged` event, which is raised after the input value is changed.

The `ValueChanged` event handler receives two parameters:

* The `sender` which is the `RadNumericInput` control;
* `Telerik.Maui.Controls.ValueChangedEventArgs` provides the following properties:

	* `PreviousValue` of type `double?` gets the old value.
	* `NewValue` of type `double?` gets the new value.

The following example demonstrates how to use the `ValueChanged` event.

**1.** Define the NumericInput:

```XAML
<telerik:RadNumericInput x:Name="numericInput" ValueChanged="RadNumericInput_ValueChanged"/>
```

**2.** Set the `ValueChanged` event:

```C#
private void RadNumericInput_ValueChanged(object sender, Telerik.Maui.Controls.ValueChangedEventArgs<double?> e)
{
   // implement your logic here
}
```

## See Also

- [Commands]({%slug numericinput-commands%})
