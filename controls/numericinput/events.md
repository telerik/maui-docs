---
title: Events
page_title: .NET MAUI NumericInput Documentation | Events
description: Check our &quot;Events&quot; documentation article for Telerik NumericInput for .NET MAUI
position: 8
previous_url: /controls/numericinput/numericinput-events
slug: numericinput-events
---

# Events

The NumericInput exposes a `ValueChanged` event, which is raised after the input value is changed.

The `ValueChanged` event handler receives two parameters:

* The `Sender` which is the RadNumericInput control;
* `ValueChangedEventArgs` provides the following properties:

	* `OldValue` of type `nullable double` gets the old value.
	* `NewValue` of type `nullable double` gets the new value.

The following example demonstrates how to use the `ValueChanged` event.

1. Define the NumericInput:

 ```XAML
<telerikInput:RadNumericInput x:Name="numericInput" ValueChanged="RadNumericInput_ValueChanged"/>
 ```

1. Add the namespace:

 ```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
 ```

1. Set the `ValueChanged` event:

 ```C#
private void RadNumericInput_ValueChanged(object sender, Telerik.XamarinForms.Input.NumericInput.ValueChangedEventArgs e)
{
   // implement your logic here
}
 ```

## See Also

- [Getting Started]({%slug numericinput-getting-started%})
- [Commands]({%slug numericinput-commands%})
