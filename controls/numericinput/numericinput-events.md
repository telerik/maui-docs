---
title: Events
page_title: .NET MAUI NumericInput Documentation | Events
description: Check our &quot;Events&quot; documentation article for Telerik NumericInput for .NET MAUI
position: 8
slug: numericinput-events
---

# Events

RadNumericInput has a `ValueChanged` event.

## ValueChanged Event

The `ValueChanged` event is raised after the input value is changed. The ValueChanged event handler receives two parameters:

* The Sender which is the RadNumericInput control;
* ValueChangedEventArgs provides the following properties:

	* `OldValue` of type nullable double - gets the old value 
	* `NewValue` of type nullable double - gets the new value

## Example

NumericInput definition

```XAML
<telerikInput:RadNumericInput x:Name="numericInput" ValueChanged="RadNumericInput_ValueChanged"/>
```

Add the namespace

```XAML
xmlns:telerikInput="clr-namespace:Telerik.XamarinForms.Input;assembly=Telerik.Maui.Controls.Compatibility"
```

The ValueChanged event definition:

```C#
private void RadNumericInput_ValueChanged(object sender, Telerik.XamarinForms.Input.NumericInput.ValueChangedEventArgs e)
{
   // implement your logic here
}
```

## See Also

- [Getting Started]({%slug numericinput-getting-started%})
- [Commands]({%slug numericinput-commands%})
